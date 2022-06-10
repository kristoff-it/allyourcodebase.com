---
title: "Web Development"
draft: false
---

## Maturity
The Zig Web Development ecosystem is still very immature.
At this stage we recommend you consider Zig only if you're interested in 
looking under the hood of modern web development. 


## Libraries / tools

## HTTP & related 
- [ducdetronquito/h11](https://github.com/ducdetronquito/h11) 
   I/O free state machine implementation of the HTTP/1.1 protocol.
- [Vexu/routez](https://github.com/Vexu/routez) 
   HTTP server written in Zig 
- [Vexu/zuri](https://github.com/Vexu/zuri) 
   URI parser written in Zig
- [Luukdegram/apple_pie](https://github.com/Luukdegram/apple_pie)
   Basic HTTP server implementation in Zig
- [truemedian/hzzp](https://github.com/truemedian/hzzp)
   A I/O agnostic HTTP/1.1 parser and encoder for Zig
- [haze/zelda](https://github.com/haze/zelda)
   async aware, Zig native http client, using zig-libressl and hzzp
   
## TLS

- [alexnask/iguanaTLS](https://github.com/alexnask/iguanaTLS)
  Minimal, experimental TLS 1.2 implementation in Zig
- [MasterQ32/zig-bearssl](https://github.com/MasterQ32/zig-bearssl)
  A BearSSL binding for Zig
- [haze/zig-libressl](https://github.com/haze/zig-libressl)
  LibreSSL stream wrappers for Zig

## Databases
- [TigerBeetle](https://tigerbeetle.com) is a distributed database for financial transactions written in Zig

### Sqlite
- [leroycep/sqlite-zig](https://github.com/leroycep/sqlite-zig)
- [vrishmann/zig-sqlite](https://github.com/vrischmann/zig-sqlite)

### Redis
- [kristoff-it/zig-okredis](https://github.com/kristoff-it/zig-okredis)

## Webby file formats

### JSON
- Available in the Zig standard library under `std.json`

### XML
- [mitchellh/zig-libxml2](https://github.com/mitchellh/zig-libxml2)

### Markdown
- [kivikakk/koino](https://github.com/kivikakk/koino)

## Templating
- [batiati/mustache-zig](https://github.com/batiati/mustache-zig)

