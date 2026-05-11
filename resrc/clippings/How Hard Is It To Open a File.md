---
title: "How Hard Is It To Open a File?"
source: "https://blog.sebastianwick.net/posts/how-hard-is-it-to-open-a-file/"
author:
  - "[[Sebastian Wick]]"
published: 2026-04-24
created: 2026-04-26
description: "It’s a question I had to ask myself multiple times over the last few months. Depending on the context the answer can be:very simple, just call the standard library function extremely hard, don’t trust anything If you are an app developer, you’re lucky and it’s almost always the first answer. If you develop something with a security boundary which involves files in any way, the correct answer is very likely the second one."
tags:
  - "clippings"
---
It’s a question I had to ask myself multiple times over the last few months. Depending on the context the answer can be:

- very simple, just call the standard library function
- extremely hard, don’t trust anything

If you are an app developer, you’re lucky and it’s almost always the first answer. If you develop something with a security boundary which involves files in any way, the correct answer is very likely the second one.

## Opening a File, the Hard Way

Like so often, the details depend on the specifics, but in the worst-case scenario, there is a process on either side of the security boundary, which operate on a filesystem tree which is shared by both processes.

Let’s say that the process with more privileges operates on a file on behalf of the process with less privileges. You might want to restrict this to files in a certain directory, to prevent the less privileged process from, for example, stealing your SSH key, and thus take a subpath that is relative to that directory.

The first obvious problem is that the subpath can refer to files outside of the directory if it contains `..`. If the privileged process gets called with a subpath of `../.ssh/id_ed25519`, you are in trouble. Easy fix: normalize the path, and if we ever go outside of the directory, fail.

The next issue is that every component of the path might be a symlink. If the privileged process gets called with a subpath of `link`, and `link` is a symlink to `../.ssh/id_ed25519`, you might be in trouble. If the process with less privileges cannot create files in that part of the tree, it cannot create a malicious symlink, and everything is fine. In all other scenarios, nothing is fine. Easy fix: resolve the symlinks, expand the path, then normalize it.

This is usually where most people think we’re done, opening a file is not that hard after all, we can all do more fun things now. Really, this is where the fun begins.

The fix above works, as long as the less privileged process cannot change the file system tree anywhere in the file’s path while the more privileged process tries to access it. Usually this is the case if you unpack an attacker-provided archive into a directory the attacker does not have access to. If it can however, we have a classic TOCTOU (time-of-check to time-of-use) race.

We have the path `foo/id_ed25519`, we resolve the smlinks, we expand the path, we normalize it, and while we did all of that, the other process just replaced the regular directory `foo` that we just checked with a symlink which points to `../.ssh`. We just checked that the path resolves to a path inside the target directory though, and happily open the path `foo/id_ed25519` which now points to your ssh key. Not an easy fix.

So, what is the fundamental issue here? A path string like `/home/user/.local/share/flatpak/app/org.example.App/deploy` describes a location in a filesystem namespace. It is *not* a reference to a file. By the time you finish speaking the path aloud, the thing it names may have changed.

The safe primitive is the file descriptor. Once you have an fd pointing at an inode, the kernel pins that inode. The directory can be unlinked, renamed, or replaced with a symlink; the fd does not care. A common misconception is that file descriptors represent open files. It is true that they can do that, but fds opened with `O_PATH` do not require opening the file, but still provide a stable reference to an inode.

The lesson that should be learned here is that you should not call any privileged process with a path. Period. Passing in file descriptors also has the benefit that they serve as proof that the calling process actually has access to the resource.

Another important lesson is that dropping down from a file descriptor to a path makes everything racy again. For example, let’s say that we want to bind mount something based on a file descriptor, and we only have the traditional mount API, so we convert the fd to a path, and pass that to mount. Unfortunately for the user, the kernel resolves the symlinks in the path that an attacker might have managed to place there. Sometimes it’s possible to detect the issue after the fact, for example by checking that the inode and device of the mounted file and the file descriptor match.

With that being said, sometimes it is not entirely avoidable to use paths, so let’s also look into that as well!

In the scenario above, we have a directory in which we want all the paths to resolve in, and that the attacker does not control. We can thus open it with `O_PATH` and get a file descriptor for it without the attacker being able to redirect it somewhere else.

With the `openat` syscall, we can open a path relative to the fd we just opened. It has all the same issues we discussed above, except that we can also pass `O_NOFOLLOW`. With that flag set, if the last segment of the path is a symlink, it does not follow it and instead opens the actual symlink inode. All the other components can still be symlinks, and they still will be followed. We can however just split up the path, and open the next file descriptor for the next path segment and resolve symlinks manually until we have done so for the entire path.

## libglnx chase

libglnx is a utility library for GNOME C projects that provides fd-based filesystem operations as its primary API. Functions like `glnx_openat_rdonly`, `glnx_file_replace_contents_at`, and `glnx_tmpfile_link_at` all take directory fds and operate relative to them. The library is built around the discipline of “always have an fd, never use an absolute path when you can use an fd.”

The most recent addition is `glnx_chaseat`, which provides safe path traversal, and was inspired by systemd’s `chase()`, and does precisely what was described above.

```c
int glnx_chaseat (int              dirfd,
                  const char      *path,
                  GlnxChaseFlags   flags,
                  GError         **error);
```

It returns an `O_PATH | O_CLOEXEC` fd for the resolved path, or -1 on error. The real magic is in the flags:

```c
typedef enum _GlnxChaseFlags {
  /* Default */
  GLNX_CHASE_DEFAULT = 0,
  /* Disable triggering of automounts */
  GLNX_CHASE_NO_AUTOMOUNT = 1 << 1,
  /* Do not follow the path's right-most component. When the path's right-most
   * component refers to symlink, return O_PATH fd of the symlink. */
  GLNX_CHASE_NOFOLLOW = 1 << 2,
  /* Do not permit the path resolution to succeed if any component of the
   * resolution is not a descendant of the directory indicated by dirfd. */
  GLNX_CHASE_RESOLVE_BENEATH = 1 << 3,
  /* Symlinks are resolved relative to the given dirfd instead of root. */
  GLNX_CHASE_RESOLVE_IN_ROOT = 1 << 4,
  /* Fail if any symlink is encountered. */
  GLNX_CHASE_RESOLVE_NO_SYMLINKS = 1 << 5,
  /* Fail if the path's right-most component is not a regular file */
  GLNX_CHASE_MUST_BE_REGULAR = 1 << 6,
  /* Fail if the path's right-most component is not a directory */
  GLNX_CHASE_MUST_BE_DIRECTORY = 1 << 7,
  /* Fail if the path's right-most component is not a socket */
  GLNX_CHASE_MUST_BE_SOCKET = 1 << 8,
} GlnxChaseFlags;
```

While it doesn’t sound too complicated to implement, a lot of details are quite hairy. The implementation uses `openat2`, `open_tree` and `openat` depending on what is available and what behavior was requested, it handles auto-mount behavior, ensures that previously visited paths have not changed, and a few other things.

## An Aside on Standard Libraries

The POSIX APIs are not great at dealing with the issue. The GLib/Gio APIs (`GFile`, etc.) are even worse and only accept paths. Granted, they also serve as a cross-platform abstraction where file descriptors are not a universal concept. Unfortunately, Rust also has this cross-platform abstraction which is based entirely on paths.

If you use any of those APIs, you very likely created a vulnerability. The deeper issue is that those path-based APIs are often the standard way to interact with files. This makes it impossible to reason about the security of composed code. You can audit your own code meticulously, open everything with `O_PATH | O_NOFOLLOW`, chain `*at()` calls carefully — and then call a third-party library that calls `open(path)` internally. The security property you established in your code does not compose through that library call.

This means that any system-level code that cares about filesystem security has to audit all transitive dependencies or avoid them in the first place.

So what would a better GLib cross-platform API look like? I would say not too different from `chaseat()`, but returning opaque handles instead of file descriptors, which on Unix would carry the `O_PATH` file descriptor and a path that can be used for printing, debugging and things like that. You would open files from those handles, which would yield another kind of opaque handle for reading, writing, and so on.

The current `GFile` was also designed to implement GVfs: `g_file_new_for_uri("smb://server/share/file")` gives you a `GFile` you can `g_file_read()` just like a local file. This is the right goal, but the wrong abstraction layer. Instead, this kind of access should be provided by FUSE, and the URI should be translated to a path on a specific FUSE mount. This would provide a few benefits:

- The fd-chasing approach works everywhere because it is a real filesystem managed by the kernel
- The filesystem becomes independent of GLib and can be used for example from Rust as well
- It stacks with other FUSE filesystems, such as the XDG Desktop Document Portal used by Flatpak

## Wait, Why Are You Talking About This?

Nowadays I maintain a small project called Flatpak. Codean Labs recently did a security analysis on it and found a number of issues. Even though Flatpak developers were aware of the dangers of filesystems, and created libglnx because of it, most of the discovered issues were just about that. One of them ([CVE-2026-34078](https://github.com/flatpak/flatpak/security/advisories/GHSA-cc2q-qc34-jprg)) was a complete sandbox escape.

`flatpak run` was designed as a command-line tool for trusted users. When you type `flatpak run org.example.App`, you control the arguments. The code that processes the arguments was written assuming the caller is legitimate. It accepted path strings, because that’s what command-line tools accept.

The Flatpak portal was then built as a D-Bus service that sandboxed apps could call to start subsandboxes — and it did this by effectively constructing a `flatpak run` invocation and executing it. This connected a component designed for trusted input directly to an untrusted caller (the sandboxed app).

Once that connection exists, every assumption baked into `flatpak run` about caller trustworthiness becomes a potential vulnerability. The fix wasn’t “change one function” — it was “audit the entire call chain from portal request to bubblewrap execution and replace every path string with an fd.” That’s commits touching the portal, `flatpak-run`, `flatpak_run_app`, `flatpak_run_setup_base_argv`, and the bwrap argument construction, plus new options (`--app-fd`, `--usr-fd`, `--bind-fd`, `--ro-bind-fd`) threaded through all of them.

If the GLib standard file and path APIs were secure, we would not have had this issue.

Another annoyance here is that the entire subsandboxing approach in Flatpak comes from 15 years ago, when unprivileged user namespaces were not common. Nowadays we could (and should) let apps use kernel-native unprivileged user namespaces to create their own subsandboxes.

Unfortunately with rather large changes comes a high likelihood of something going wrong. For a few days we scrambled to fix a few regressions that prevented Steam, WebKit, and Chromium-based apps from launching. Huge thanks to Simon McVittie!

In the end, we managed to fix everything, made Flatpak more secure, the ecosystem is now better equipped to handle this class of issues, and hopefully you learned something as well.

---

Do you have a comment?

Toot at me on [mastodon](https://hachyderm.io/@swick) or send me a [mail](mailto:sebastian@sebastianwick.net)!

---

- [How Hard Is It To Open a File?](https://blog.sebastianwick.net/posts/how-hard-is-it-to-open-a-file/)
- [Three Little Rust Crates](https://blog.sebastianwick.net/posts/three-little-rust-crates/)
- [Redefining Content Updates in Wayland](https://blog.sebastianwick.net/posts/wayland-content-updates/)
	Mar 10, 2026
- [Best Practices for Ownership in GLib](https://blog.sebastianwick.net/posts/glib-ownership-best-practices/)
- [Improving the Flatpak Graphics Drivers Situation](https://blog.sebastianwick.net/posts/flatpak-graphics-drivers/)
	Jan 6, 2026
- [Flatpak Pre-Installation Approaches](https://blog.sebastianwick.net/posts/flatpak-pre-installation/)
	Dec 13, 2025
	Tags:
	- [flatpak](https://blog.sebastianwick.net/tags/flatpak)
	- [system integration](https://blog.sebastianwick.net/tags/system-integration)
- [Flatpak Happenings](https://blog.sebastianwick.net/posts/flatpak-happenings/)
- [SO\_PEERPIDFD Gets More Useful](https://blog.sebastianwick.net/posts/so-peerpidfd-gets-more-useful/)
- [XDG Intents Updates](https://blog.sebastianwick.net/posts/xdg-intents-update/)
	Sep 24, 2025
- [Integrating libdex with GDBus](https://blog.sebastianwick.net/posts/libdex-gdbus/)
- [Testing with Portals](https://blog.sebastianwick.net/posts/testing-with-portals/)
	Aug 21, 2025
- [Display Next Hackfest 2025](https://blog.sebastianwick.net/posts/display-next-hackfest-2025/)
	Aug 15, 2025
- [GNOME 49 Backlight Changes](https://blog.sebastianwick.net/posts/gnome-49-backlight-changes/)
- [Blender HDR and the reference white issue](https://blog.sebastianwick.net/posts/blender-hdr-reference-white/)
- [Booting into Toolbox Containers](https://blog.sebastianwick.net/posts/booting-into-toolbox-containers/)
- [On the Usefulness of SO\_PEERPIDFD](https://blog.sebastianwick.net/posts/so-peerpidfd-usefulness/)
- [Fedora Silverblue Development Utils](https://blog.sebastianwick.net/posts/silverblue-development-utils/)
	Aug 31, 2023
- [Developing Gnome Shell on Fedora Silverblue](https://blog.sebastianwick.net/posts/silverblue-gnome-shell-development/)
- [Setting up a personal server in 2023](https://blog.sebastianwick.net/posts/personal-server-in-2023/)