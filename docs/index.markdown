---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults
title:  "Blessed C"
layout: home
---
## Tooling

<div class="table-wrapper" markdown="block">

|Use Case|Recommended Tools|
|---|---|
|Toolchain|[**GCC C Compiler**](https://gcc.gnu.org/) <br> Widely used compiler for Un*x system. <br> [**Clang**](https://clang.llvm.org/) <br> A C frontend that compiles C into LLVM IR. Also very popular. <br> [**MSVC**](https://visualstudio.microsoft.com/) <br> Microsoft's C compiler toolchain, mainly for Windows. |
|Build Systems|[**Autotools**](https://www.gnu.org/software/automake/manual/html_node/GNU-Build-System.html) <br> One of the most widely used build systems (configure && make). <br> [**CMake**](https://cmake.org) <br> The de-facto standard for building modern C/C++ code.|
|Benchmarking|[**b63**](https://github.com/okuvshynov/b63) <br> Light-weight micro-benchmarking tool. Not very popular and maybe only suitable for personal use. <br> [**hyperfine**](https://github.com/sharkdp/hyperfine) <br> Tool for benchmarking compiled binaries (similar to unix time command but better). |
|Language Server|[**clangd**](https://clangd.llvm.org) <br> Adds smart features to your editor: code completion, compile errors, go-to-definition and more.|

</div>

## Common
Very common tools that every C developer should know about.

### General
General use case.

<div class="table-wrapper" markdown="block">

|Use Case|Recommended Tools|
|---|---|
|Regular Expressions|[**hyperscan**](https://github.com/intel/hyperscan) <br> Intel's high-performance multi-thread text matching library. Use a well-designed callback-style API and may be too complex for simple use cases. <br> [**cre2**](https://github.com/marcomaggi/cre2) <br> C wrapper of Google's re2 library. Easier to use, but inactively maintained.|
|UUIDs|[**uuid4**](https://github.com/rxi/uuid4) <br> Simple implementation of UUID v4. Unmaintained. |
|Gzip (de)compression|[**zlib**](https://github.com/madler/zlib) <br> Official zlib library.|

</div>
### (De)serialization

<div class="table-wrapper" markdown="block">

|Use Case|Recommended Tools|
|---|---|
|CSV|[**zsv**](https://github.com/liquidaty/zsv) <br> Fast (simd) CSV parser.|
|JSON|[**json.h**](https://github.com/sheredom/json.h) <br> Single header JSON parser. <br> [**parson**](https://github.com/kgabis/parson) <br> Two-file, C89-compliant JSON parser.|
|INI|[**inih**](https://github.com/benhoyt/inih) <br> Single header INI file parser, good for embedded systems.  |
|YAML|[**libyaml**](https://github.com/yaml/libyaml) <br> Official YAML parser, but inactive for a while.|
|TOML|[**tomlc99**](https://github.com/cktan/tomlc99) <br> C99-compliant TOML parser.|
|XML|[**libexpat**](https://github.com/libexpat/libexpat) <br> Fast streaming XML parser, C99-compliant.|
|HTML|[**lexbor**](https://github.com/lexbor/lexbor) <br> Not just a parser, but a full-featured HTML5 Renderer. It has HTML (de)serialization support. <br> [**myhtml**](https://github.com/lexborisov/myhtml) <br> A standalone HTML parser by the same author of lexbor. It has been deprecated in favor of lexbor.|

</div>

### Language Extensions
Try to add (or "simulate") some modern language features to C.

<div class="table-wrapper" markdown="block">

|Use Case|Recommended Tools|
|---|---|
|Algebraic Data Types|[**datatype99**](https://github.com/Hirrolot/datatype99) <br> Intuitive algebraic data types with exhaustive pattern matching & compile-time introspection facilities. |
|Object-Oriented Programming|[**obj.h**](https://github.com/small-c/obj.h) <br> Single header OOP support. Inactive for a while. |

</div>

## I/O & Networking
Networking is the dullest part of C programming.

### Async Foundation
<div class="table-wrapper" markdown="block">

|Use Case|Recommended Tools|
|---|---|
|Async I/O|[**libuv**](https://github.com/libuv/libuv) <br> Async library for TCP/UDP/DNS/IPC/Singal Handling/File Operations. Primarily developed for Node.js.|

</div>

### Protocol Support
<div class="table-wrapper" markdown="block">

|Use Case|Recommended Tools|
|---|---|
|HTTP|[**libhv**](https://github.com/ithewei/libhv) <br> Full-featured async library for TCP/UDP/HTTP(S)/WebSocket client/server/proxy, and MQTT client.|
|gRPC|**Note**: Unfortunately, there is no good gRPC library for C. The best way to use gRPC in C is to use the C++ bindings.|

</div>

## Command-Line Tool

### Argument Parsing
<div class="table-wrapper" markdown="block">

|Use Case|Recommended Tools|
|---|---|
|POSIX/BSD-style (`-cvf`)| **getopt** <br> In POSIX specification, getopt is the standard method to parse command-line arguments. <br> [**getopt_long**](https://www.gnu.org/software/libc/manual/html_node/Getopt-Long-Options.html) <br> GNU extension of getopt that supports long options (--foo=bar) and has been widely accepted. Included in glibc and gnulib. <br> [**argparse**](https://github.com/cofyc/argparse) <br> Standalone argument parser supporting subcommands. Inactive for a while. <br> [**optparse**](https://github.com/skeeto/optparse) <br> Standalone, single-header argument parser, designed to prevent global variables, support resetting and printing error message to elsewhere instead of stderr, compared with getopt. Inactive for a while. <br> [**cmd_arger**](https://github.com/heroseh/cmd_arger) <br> A nice argument parser with declarative syntax and auto-generated help message. Inactive for a while.|
| DOS-style (`/C /V /F`) |[**getopt-dos**](https://github.com/ofey404/getopt-dos) <br> Like getopt, but supports DOS-style options. Not mature and unmaintained.|

</div>


### Terminal Rendering
<div class="table-wrapper" markdown="block">

|Use Case|Recommended Tools|
|---|---|
|Progress indicators| [**progressbar**](https://github.com/doches/progressbar) <br>  An easy-to-use C library for displaying text progress bars. Inactive for a while.|
|TUI|[**ncurses**](https://gnu.org/software/ncurses) <br> De facto standard library for TUI. Only Un*x support. <br> [**pdcurses**](https://github.com/wmcbrine/PDCurses) <br> A curses implementation for DOS, OS/2, Windows console, X11 and SDL. |
|Interactive prompts| [**readline**](https://www.gnu.org/software/readline/) <br> De facto standard GNU library for interactive inputs. Bash is actually built on it, which supports history, completion, and line editing features. <br> [**linenoise**](https://github.com/antirez/linenoise) <br> A small, self-contained alternative to readline and libedit. Only Un*x support, and being inactive for a while.|

</div>