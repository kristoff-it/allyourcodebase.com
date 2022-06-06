---
title: "The Zig Programming Language"
draft: false
---

{{% details "Commonly Asked Questions" false %}}

## When will Zig reach v1.0?
Zig will be tagged v1 once:
- all planned language features have been implemented
- the full language spec has been published
- all known bugs have been solved
- stdlib has gone through a full release cycle without any change

**If you want to help us move forward faster, 
[consider donating](https://ziglang.org/zsf/) 
so that we can pay more contributors for their time.**

## Is Zig made by a big tech company?
No, Zig is supported by the Zig Software Foundation, a 501(c)(3) non-profit 
company. We will never concede board seats to any big tech company.

[Learn more about the ZSF](https://ziglang.org/zsf/)
{{% /details %}}

## Is Zig production-ready?
The Zig compiler toolchain is being used to cross-compile C/C++/ObjC
[by Uber](https://jakstys.lt/2022/how-uber-uses-zig/) and a few other 
companies.

The Zig programming language is not being used in production by any big
company and it's currently not recommended to use Zig for mission-critical
software as the language is still under development and there are 
[known bugs](https://github.com/ziglang/zig/issues?q=is%3Aopen+is%3Aissue+label%3Abug)
and even some 
[miscompilations](https://github.com/ziglang/zig/issues?q=is%3Aopen+is%3Aissue+label%3Amiscompilation).

Some companies are preparing to be early adopters for when Zig becomes more 
suitable for production use. One example is [Coil](https://coil.com), which is
working on [TigerBeetle](https://tigerbeetle.com).

We know of [some cases](https://www.youtube.com/watch?v=124wdTckHNY) where Zig 
is being used in production despite its immaturity.

**If you want to help us move forward faster, 
[consider donating](https://ziglang.org/zsf/) 
so that we can pay more contributors for their time.**

## Self-Hosting 
Zig is not self-hosted yet, but we're almost there. 
Zig 0.10.0 will be released once the self-hosted compiler is ready to ship. 
[Follow #89](https://github.com/ziglang/zig/issues/89) to track our progress. 

Self-hosting is the first of a series of updates to Zig aimed at improving 
compilations speed and lowering memory usage (while compiling). See 
[Zig Roadmap 2023](https://www.youtube.com/watch?v=AqDdWEiSwMM) for more info.

## Official Package Manager 
Zig will have an official package manager. Its development is scheduled for 
right after the self-hosted compiler is released. For now the choices that will 
probably be part of the first design iteration are:

- No official package repository
- Minimal Version Selection
- v1+ packages can only depend on v1+ packages

## Async/Await and Event Loop
Async/Await is implemented in the language but still lacks one important 
operator that would allow to `await` on multiple async frames at once.
Aside from that, it's already possible to write libraries that can work 
seamlessly in both blocking and evented I/O mode, like 
[zig-okredis](https://github.com/kristoff-it/zig-okredis), as well as 
full-fledged evented applications like [bork](https://github.com/kristoff-it/bork).

The event loop is part of the standard libary, which means that it's possible
to use custom implementations with relative ease. The current implementation 
in the standard library is of PoC quality. Improvements on the event loop depend 
on finalizing the design of async/await and so it also depends on the 
self-hosted compiler.

// TODO: list some event loop implementations by the community

News about evented I/O support in Zig:
- Apr 2022 [kprotty contributes std.Treap](https://github.com/ziglang/zig/pull/11444) 
  and [a few](https://github.com/ziglang/zig/pull/11523) other 
  [improvements](https://github.com/ziglang/zig/pull/11497) to Zig's atomic primitives
- Apr 2022 [kprotty's Futex RWLock algorithm gets merged into Rust](https://github.com/rust-lang/rust/pull/95801)
- May 2021 [kprotty joins the core team](https://old.reddit.com/r/Zig/comments/no28b9/please_welcome_kprotty_to_the_core_zig_team/)
- Sep 2020 [Joran Dirk Greef adds io_uring support to the stdlib](https://github.com/ziglang/zig/pull/6356)

## Standard Library
Currently the Zig standard library is the result of organic growth. While fairly
complete and reasonably well designed, it was never the focus of the main 
development effort and as such it will occasionally have confusing corners and
missing features.

The current plan is to start an official polishing effort at some point after
development of the language itself nears completion. This means completing the
transition to the self-hosted compiler implementation and also going through
the current backlog of language features that are accepted but not yet 
implemented.

## Standard Library Documentation
The official website lists in the Learn section a link to a build of the 
[stdlib docs](https://ziglang.org/documentation/master/std/). Those docs are
marked as experimental and as such are not linked on the front page of 
ziglang.org and a red banner at the top recommends reading the stdlib source
code instead, liking to [a guide on how to do so](https://github.com/ziglang/zig/wiki/How-to-read-the-standard-library-source-code).

Those docs are generated automatically by the bootstrap compiler using a 
strategy that, among various things, makes it impossible for the docs to see
declarations that are never referenced, on top of being tightly integrated
with the old compiler, making adding any improvement to it a waste of effort.

Loris Cro has started a new effort to implement automated doc generation for 
the self-hosted compiler. You can learn more 
[here](https://github.com/ziglang/zig/wiki/How-to-contribute-to-Autodoc), and 
you can follow along with the livecoding sessions on 
[Loris Cro's Twitch stream](https://twitch.tv/kristoff_it).

The new doc implementation is far from complete, but it has already surpassed
the old implementation in a few key areas and so it will soon be merged into
master branch to replace the old code (while still maintaining the 
*experimental* attribute).


