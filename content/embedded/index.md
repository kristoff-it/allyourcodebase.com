---
title: "Zig on Embedded"
draft: false
---

## Maturity

The Zig embedded space is relatively new and is being actively explored. The [Zig Embedded Group](https://github.com/ZigEmbeddedGroup) was created by members of the community to organize the effort.

This is exciting work considering Zig's apparent fit for embedded systems. The standard library can be used unmodified on freestanding targets thanks to explicit allocation, comptime is extremely useful for things like precalculated lookup tables, and the unfinished C backend (part of the stage 2 compiler) means we'll be able to target exotic architectures that LLVM can't.

# MicroZig

[MicroZig](https://github.com/ZigEmbeddedGroup/microzig) is infrastructure for an embedded project. It provides an easy-to-use build function that will generate a linkerscript for you under the hood. It _is_ a bit of a kitchen sink and often has breaking changes as new patterns and features are created.

# Libraries / Tools

[Regz](https://github.com/ZigEmbeddedGroup/regz) is a code generator for register access. It currently accepts SVD and ATDF file formats, most commonly used for ARM and AVR architectures. Code generated with Regz is usable with MicroZig or on its own.
