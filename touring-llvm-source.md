# touring-llvm-source

This is chapter two of [[learning-compilers-01|Learning Compilers Chapter 01]]

## Core libraries and additions

- `llc`: LLVM static compiler. Takes a file written in LLVM-IR as input and compiles it.
- `llvm-objdump` and `llvm-dwarfdump`: lets you inspect object files.
- `llvm-ar`: lets you archive object files.
- Polly project: sets of optimizations for LLVM based on a mathematical representation of
  a **polyhedral model**. Found in the `polly` directory.
- MLIR project: multi-level intermediate representation of LLVM. Makes LLVM IR extensible
  and capture this information in a domain-specific representation. Found in the `mlir`
  directory.

## Compilers and tools

- `clang`: compiler for C/C++/Objective-C/Objective-C++.
- `clang-format`: formats C/C++ source files and source fragments according to rules
  provided by the user. Aims to be compatible with gcc and Microsoft's C/C++ compiler.

### Additional tools for C/C++

These are provided by `clang-tools-extra` project in the directory of the same name.

- `clang-tidy`: lint style checker for C/C++.
- `llgo`: Go programming language compiler for easy interfacing with LLVM. Unmaintained.
- `lld`: LLVM linker. Supports ELF, COFF, Mach-O, and WebAssembly formats.
- `lldb`: Debugger for LLVM. Similar to GDB and supports C, C++ and Objective C/C++ out of
  the box.

## Runtime libraries
