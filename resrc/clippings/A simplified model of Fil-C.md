---
title: "A simplified model of Fil-C"
source: "https://www.corsix.org/content/simplified-model-of-fil-c"
author:
  - "[[corsix.org]]"
published: 2026-04-17
created: 2026-04-18
description:
tags:
  - "clippings"
---
I've seen lots of chatter about [Fil-C](https://fil-c.org/) recently, which pitches itself as a memory safe implementation of C/C++. You can read the [gritty details](https://fil-c.org/invisicaps) of how this is achieved, but for people coming across it for the first time, I think there is value in showing a simplified version, as once you've understood the simplified version it becomes a smaller mental step to then understand the production-quality version.

The real Fil-C has a compiler pass which rewrites LLVM IR, whereas the simplified model is an automated rewrite of C/C++ source code: unsafe code is transformed into safe code. The first rewrite is that within every function, every local variable of pointer type gains an accompanying local variable of `AllocationRecord*` type, for example:

| Original Source | After Fil-C Transform |
| --- | --- |
| ``` void f() {   T1* p1;   T2* p2;   uint64_t x;   ... ``` | ``` void f() {   T1* p1; AllocationRecord* p1ar = NULL;   T2* p2; AllocationRecord* p2ar = NULL;   uint64_t x;   ... ``` |

Where `AllocationRecord` is something like:

```
struct AllocationRecord {
  char* visible_bytes;
  char* invisible_bytes;
  size_t length;
};
```

Trivial operations on local variables of pointer type are rewritten to also move around the `AllocationRecord*`:

| Original Source | After Fil-C Transform |
| --- | --- |
| `p1 = p2;` | `p1 = p2, p1ar = p2ar;` |
| `p1 = p2 + 10;` | `p1 = p2 + 10, p1ar = p2ar;` |
| `p1 = (T1*)x;` | `p1 = (T1*)x, p1ar = NULL;` |
| `x = (uintptr_t)p1;` | `x = (uintptr_t)p1;` |

When pointers are passed-to or returned-from functions, the code is rewritten to include the `AllocationRecord*` as well as the original pointer. Calls to *particular* standard library functions are additionally rewritten to call Fil-C versions of those functions. Putting this together, we get:

| Original Source | After Fil-C Transform |
| --- | --- |
| ``` p1 = malloc(x); ... free(p1); ``` | ``` {p1, p1ar} = filc_malloc(x); ... filc_free(p1, p1ar); ``` |

The (simplified) implementation of `filc_malloc` actually performs three distinct allocations rather than just the requested one:

```
void* filc_malloc(size_t length) {
  AllocationRecord* ar = malloc(sizeof(AllocationRecord));
  ar->visible_bytes = malloc(length);
  ar->invisible_bytes = calloc(length, 1);
  ar->length = length;
  return {ar->visible_bytes, ar};
}
```

When a pointer variable is dereferenced, the accompanying `AllocationRecord*` is used to perform bounds checks:

| Original Source | After Fil-C Transform |
| --- | --- |
| ``` x = *p1; ... *p2 = x; ``` | ``` assert(p1ar != NULL); uint64_t i = (char*)p1 - p1ar->visible_bytes; assert(i < p1ar->length); assert((p1ar->length - i) >= sizeof(*p1)); x = *p1; ... assert(p2ar != NULL); uint64_t i = (char*)p2 - p2ar->visible_bytes; assert(i < p2ar->length); assert((p2ar->length - i) >= sizeof(*p2)); *p2 = x; ``` |

Things become more interesting when the value being stored or loaded is itself a pointer. As already seen, local variables of pointer type have their accompanying `AllocationRecord*` variable inserted by the compiler, which the compiler can do because it has full control and visibility of all local variables. Once pointers exist in the heap rather than just in local variables, things become harder, but this is where `invisible_bytes` comes in: if there is a pointer at `visible_bytes + i`, then its accompanying `AllocationRecord*` is at `invisible_bytes + i`. In other words, `invisible_bytes` is an array with element type `AllocationRecord*`. To ensure sane access to this array, `i` must be a multiple of `sizeof(AllocationRecord*)`. The extra logic for this is highlighted in green:

| Original | After Fil-C Transform |
| --- | --- |
| ``` p2 = *p1; ... *p1 = p2; ``` | ``` assert(p1ar != NULL); uint64_t i = (char*)p1 - p1ar->visible_bytes; assert(i < p1ar->length); assert((p1ar->length - i) >= sizeof(*p1)); assert((i % sizeof(AllocationRecord*)) == 0); p2 = *p1; p2ar = *(AllocationRecord**)(p1ar->invisible_bytes + i); ... assert(p1ar != NULL); uint64_t i = (char*)p1 - p1ar->visible_bytes; assert(i < p1ar->length); assert((p1ar->length - i) >= sizeof(*p1)); assert((i % sizeof(AllocationRecord*)) == 0); *p1 = p2; *(AllocationRecord**)(p1ar->invisible_bytes + i) = p2ar; ``` |

One thing we've not yet seen is `filc_free`, which does something like:

```
void filc_free(void* p, AllocationRecord* par) {
  if (p != NULL) {
    assert(par != NULL);
    assert(p == par->visible_bytes);
    free(par->visible_bytes);
    free(par->invisible_bytes);
    par->visible_bytes = NULL;
    par->invisible_bytes = NULL;
    par->length = 0;
  }
}
```

The eagle-eyed will note that `filc_malloc` made three allocations, but `filc_free` only frees two of them: the `AllocationRecord` object isn't freed by `filc_free`. This gap gets covered by the addition of a garbage collector (GC). You heard that right - this is C/C++ with a GC. The production-quality Fil-C has a [parallel concurrent incremental collector](https://fil-c.org/fugc), but a stop-the-world collector suffices for a simple model. The collector traces through `AllocationRecord` objects, and frees any unreachable ones. It also does two more things:

1. Upon freeing an unreachable `AllocationRecord`, call `filc_free` on it.
2. If an `AllocationRecord` has length 0, any pointers to that `AllocationRecord` will be changed to point at a single canonical `AllocationRecord` with length 0.

Point 1 means that if you're using Fil-C, forgetting to call `free` is no longer a memory leak: the memory will be automatically freed by the GC. That isn't to say that calling `free` is useless, as it allows memory to be freed earlier than the GC might otherwise choose to. Point 2 means that after calling `free` on something, the accompanying `AllocationRecord` will eventually become unreachable, and thus itself eventually be freed.

Once a GC is present, it becomes tempting to use it more. One such use is making it safe to take the address of local variables, even if the resultant pointer is used after the local variable goes out of scope. If the compiler sees that a local variable has its address taken, and cannot *prove* that the address doesn't escape beyond the lifetime of the local variable, then the Fil-C transform will promote that local variable to be heap-allocated via `malloc` rather than stack-allocated. A matching `free` doesn't need to be inserted, as the GC will pick it up.

The final thing I want to highlight is the Fil-C version of `memmove`. This function from the C standard library manipulates arbitrary memory, and the compiler has no knowledge of what pointers might be present in that memory. To get past this problem, a reasonable heuristic is used: any pointers within arbitrary memory need to be *completely* within arbitrary memory, and need to be correctly aligned. This has the interesting consequence that `memmove` of eight aligned bytes behaves differently to eight separate 1-byte `memmove` s of the constituent bytes: the former will also `memmove` the corresponding range of `invisible_bytes`, whereas the latter will not.

That wraps up the simplified model. Some of the additional complications in the production-quality version include:

- **Threads:** Concurrency makes the GC more complex. It also means that `filc_free` can't *immediately* free anything, as the free-ing thread might be racing with a different thread trying to access the underlying memory. Atomic operations on pointers also need some extra magic, as the default rewriting of a pointer load or store is to two loads or stores, which breaks atomicity.
- **Function pointers:** An additional piece of metadata in `AllocationRecord` is used to denote that the `visible_bytes` pointer is a pointer to executable code rather than regular data. Calls through a function pointer `p1` check that `p1 == p1ar->visible_bytes` and that `p1ar` denotes a function pointer. To avoid type confusion attacks on function pointers, the function calling ABI also needs to verify that the type signature is correct. One way of doing this is to make *all* functions take the same type signature: all parameters are passed as if they were packed into a structure and passed through memory, and at ABI boundaries, every function expects to receive just a single `AllocationRecord` corresponding to that structure.
- **Memory usage optimization:** It is very tempting to have `filc_malloc` avoid immediately allocating `invisible_bytes`, and instead allocate it on-demand later should it ever be required. It is also tempting to colocate the `AllocationRecord` and `visible_bytes` into a single allocation. If the underlying `malloc` prepends metadata to every allocation, it looks tempting to put that metadata in `AllocationRecord` instead.
- **Performance optimization:** Memory safety in Fil-C comes at a performance cost, so it is worth playing various tricks to claw back some of that lost performance.

With the baseline understanding in place, I want to finish on a question: when might you want to use Fil-C? Personally, my answers are:

1. You have a large quantity of C/C++ code which seems to work, but it hasn't been proven memory-safe, and you're willing to introduce a GC and take a large performance hit in exchange for memory safety (perhaps as a temporary measure until you rewrite in Java or Go or Rust).
2. Just like you can run C/C++ code under [ASan](https://clang.llvm.org/docs/AddressSanitizer.html) to find memory bugs, you can run it under Fil-C to find memory bugs.
3. If you have a language with a strong compile-time story, and the compile-time language is the same as the runtime language (for example, [Zig](https://ziglang.org/)), you could use a Fil-C setup for safe compile-time evaluation, even if runtime evaluation is unsafe.
4. Some people like to contemplate [pointer provenance](https://www.ralfj.de/blog/2020/12/14/provenance.html). If you've not come across this concept before, here's a nerd-snipe question: assuming `p1` and `p2` have the same type, is it valid for a compiler to rewrite `if (p1 == p2) { f(p1); }` to `if (p1 == p2) { f(p2); }`? In Fil-C, the answer is clearly "no", as it changes which `AllocationRecord*` gets passed along to `f`. This makes Fil-C a useful example of a concrete system which has pointer provenance.