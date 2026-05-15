Things I should Know


1. let is use to declare variables and functions both. 
2. rec keyword is used to define recursive functions that will call themselves
3. prefix and infix operators
4. `|>` i.e. pipe also called the reverse application operator
5. Application operator which goes the other way is `@@`, useful for reducing the number of parens when doing composition
6. Functions can be defined with the `function` keyword in which case they can use built in pattern matching.
7. Patterns can be used to extract data from a list
8. prefer `String.concat` over the pairwise operator `^` for string concatenation
9. Use functions like `List.fold` and `List.reduce` to work effectively with lists.
10. `List.filter` and `List.filter_map` can be used to filter lists to extract subsets of it.
11. `List.partition_tf` can be used to partition a list into two parts one where the condition is true and one where the condition is false
12. `List.append` or its operator form `@` can be used to merge two lists
13. `List.concat` will concatenate a list of lists
14. Using tail recursion by using an accumulator will prevent stack frames from overflowing
15. The invocation is considered a tail call when the caller doesn’t do anything with the value returned by the callee except to return it.
16.  The tail-call optimization makes sense because, when a caller makes a tail call, the caller’s stack frame need never be used again, and so you don’t need to keep it around. Thus, instead of allocating a new stack frame for the callee, the compiler is free to reuse the caller’s stack frame.
17. Tail recursion is important for more than just lists. Ordinary non-tail recursive calls are reasonable when dealing with data structures like binary trees, where the depth of the tree is logarithmic in the size of your data. But when dealing with situations where the depth of the sequence of nested calls is on the order of the size of your data, tail recursion is usually the right approach.
18. Use `as` and `when` to make your functions using pattern matching terser.
19. The takeaway from all of this is although `when` clauses can be useful, we should prefer patterns wherever they are sufficient.
20. The idiom of writing `let () =` may seem a bit odd, but it has a purpose. The `let` binding here is a pattern-match to a value of type `unit`, which is there to ensure that the expression on the right-hand side returns `unit`, as is common for functions that operate primarily by side effect. If we weren’t using `Base` or any other external libraries, we could build the executable like this:
21. 
