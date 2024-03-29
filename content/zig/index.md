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

## Production-Ready Status
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

Starting [from version 0.10.0](https://ziglang.org/download/0.10.0/release-notes.html), 
Zig started shipping the self-hosted compiler.

Version 0.10.0 still also includes the bootstrap compiler, which can be enabled
with `-fstage1`. Starting from 0.11.0 (not yet released at the moment of writing)
the bootstrap compiler will be deleted and all code will have to be built using
the self-hosted implementation.

Self-hosting is the first of a series of updates to Zig aimed at improving 
compilations speed and lowering memory usage (while compiling). See 
[Zig Roadmap 2023](https://www.youtube.com/watch?v=AqDdWEiSwMM) for more info.

## Official Package Manager 
Zig will have an official package manager. Its development will start after the
release of the self-hosted compiler. For now the choices that will 
probably be part of the first design iteration are:

- No official package repository
- Minimal Version Selection
- v1+ packages can only depend on v1+ packages

Andrew gave [a talk at Software You Can Love 2022](https://www.youtube.com/watch?v=stChOsejLEQ) 
on the subject.


## Async/Await and Event Loop
Async/Await is implemented in the language but still lacks one important 
operator that would allow to `await` on multiple async frames at once.
Aside from that, it's already possible to write libraries that can work 
seamlessly in both blocking and evented I/O mode, like 
[zig-okredis](https://github.com/kristoff-it/zig-okredis), as well as 
full-fledged evented applications like [bork](https://github.com/kristoff-it/bork).

The event loop is part of the standard libary, which means that it will be eventually 
possible to use custom implementations with relative ease. The current implementation 
in the standard library is of PoC quality. Improvements on the event loop depend 
on finalizing the design of async/await.


// TODO: list some event loop implementations by the community

News about evented I/O support in Zig:
- Oct 2022 ["Zig's I/O and Concurrency Story" by kprotty](https://www.youtube.com/watch?v=Ul8OO4vQMTw)
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
[stdlib docs](https://ziglang.org/documentation/master/std/). 

These docs are marked as `beta` and as such you should expect to find bugs
and missing information. The automated doc system is being actively worked on
and [is accepting contributions](https://github.com/ziglang/zig/wiki/How-to-contribute-to-Autodoc).

While stdlib docs are already mostly usable, we still recommend you familiarize
yourself with [the stdlib source code](https://github.com/ziglang/zig/wiki/How-to-read-the-standard-library-source-code),
as it will help you make up for the current deficienties of the automated doc
system.