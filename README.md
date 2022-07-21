# Langdev libraries for Rust

- [Lexers](#lexers)
- [Parsers](#parsers)
- [Codegen](#codegen)
- [String interning](#string-interning)
- [Just-in-time compilation](#just-in-time-compilation)
- [Error reporting](#error-reporting)
- [Language server protocol](#language-server-protocol)
- [Testing](#testing)
- [Incremental compilation](#incremental-compilation)
- [Floats/Ints/Bools](#floatsintsbools)
- [Binary & object file parsing, generating and processing](#binary--object-file-parsing-generating-and-processing)
- [Solvers](#solvers)
- [CLI](#cli)
  - [Configuration](#configuration)
- [Repl](#repl)
- [String handling](#string-handling)
- [Syntax trees](#syntax-trees)
- [Pretty printing](#pretty-printing)
- [Variable binding](#variable-binding)
- [Caching](#caching)
- [WASM](#wasm)
- [Logging](#logging)
- [Storage](#storage)
  - [Disjoint-sets](#disjoint-sets)
- [Incremental Analysis](#incremental-analysis)
  - [Timely Dataflow Resources](#timely-dataflow-resources)
- [Fuzzing](#fuzzing)
  - [Fuzzing Resources](#fuzzing-resources)
- [Graphs](#graphs)
- [Type Checking](#type-checking)
- [Peephole Optimization](#peephole-optimization)
- [Garbage Collection](#garbage-collection)
- [Guides & Resources](#guides--resources)
  - [Type Checking](#type-checking-1)
  - [Inlining](#inlining)
  - [RVSDG](#rvsdg)
  - [Equality Saturation](#equality-saturation)

## Lexers

- [`logos`](https://crates.io/crates/logos) Logos has two goals: To make it easy to create a Lexer, so you can focus on more complex problems and to make the generated Lexer faster than anything you'd write by hand
- [`lrlex`](https://crates.io/crates/lrlex) A replacement for [`lex`](http://dinosaur.compilertools.net/lex/index.html)/[`flex`](https://westes.github.io/flex/manual/) that generates Rust code
    
## Parsers

- [`lalrpop`](https://crates.io/crates/lalrpop) A convenient LR(1) parser generator
- [`nom`](https://crates.io/crates/nom) A byte-oriented, zero-copy, parser combinators library
- [`combine`](https://crates.io/crates/combine) Fast parser combinators on arbitrary streams with zero-copy support.
- [`pom`](https://crates.io/crates/pom) PEG parser combinators using operator overloading without macros.
- [`peg`](https://crates.io/crates/peg) A simple Parsing Expression Grammar (PEG) parser generator.
- [`glue`](https://crates.io/crates/glue) Glue is a parser combinator framework for parsing text based formats, it is easy to use and relatively fast too
- [`pratt`](https://crates.io/crates/pratt) A general purpose pratt parser for Rust
- [`pest`](https://crates.io/crates/pest) A general purpose parser written in Rust with a focus on accessibility, correctness, and performance using parsing expression grammars (PEG)
- [`lrpar`](https://crates.io/crates/lrpar) A Yacc-compatible parser.
  - [`nimbleparse_lsp`](https://github.com/ratmice/nimbleparse_lsp) An LSP server for quickly developing lrpar parsers, which parses input buffers on grammar change bypassing code generation.
- [`tree-sitter`](https://tree-sitter.github.io/tree-sitter/) A parser generator for building fast editor-friendly parsers with features like streaming, incremental, resumable (re)parsing, with timeouts and cancellations, and advanced syntax node queries.
- [`rowan`](https://crates.io/crates/rowan) Generic lossless syntax trees
  - [`ungrammar`](https://crates.io/crates/ungrammar) A DSL for specifying concrete syntax trees, see [this introductory post](https://rust-analyzer.github.io/blog/2020/10/24/introducing-ungrammar.html)
- [`cstree`](https://crates.io/crates/cstree) A fork of `rowan` with threadsafe syntax trees and built-in [source string interning](#string-interning)
- [`chomp`](https://crates.io/crates/chomp) Chomp is a fast monadic-style parser combinator library designed to work on stable Rust
- [`oak`](https://crates.io/crates/oak) A typed parser generator embedded in Rust code for Parsing Expression Grammars
- [`chumsky`](https://crates.io/crates/chumsky) A friendly parser combinator crate that makes writing LL(k) parsers with error recovery easy
    
## Regular expressions

- [`regex`](https://crates.io/crates/regex) An implementation of regular expressions for Rust. This implementation uses finite automata and guarantees linear time matching on all inputs.
- [`regress`](https://crates.io/crates/regress) A regular expression engine targeting EcmaScript syntax.
- [`onig`](https://crates.io/crates/onig) Rust-Onig is a set of Rust bindings for the Oniguruma regular expression library. 

## Codegen

- [`cranelift`](https://crates.io/crates/cranelift) Cranelift is a low-level retargetable code generator
- [`llvm-sys`](https://crates.io/crates/llvm-sys) Bindings to LLVM's C API
- [`iced-x86`](https://crates.io/crates/iced-x86) A blazing fast and correct x86/x64 disassembler, assembler and instruction decoder
- [`llama`](https://crates.io/crates/llama) Friendly LLVM bindings
- [`inkwell`](https://crates.io/crates/inkwell) Inkwell aims to help you pen your own programming languages by safely wrapping llvm-sys
- [`llvm-ir`](https://crates.io/crates/llvm-ir) LLVM IR in natural Rust data structures
- [`llvmenv`](https://crates.io/crates/llvmenv) Manage multiple LLVM/Clang builds
- [`walrus`](https://crates.io/crates/walrus) A library for performing WebAssembly transformations
- [`cilk`](https://github.com/maekawatoshiki/cilk) Toy Compiler Infrastructure influenced by LLVM written in Rust.

## String interning

- [`lasso`](https://crates.io/crates/lasso) A multithreaded and single threaded string interner with a minimal memory footprint and arena allocation
- [`string-interner`](https://crates.io/crates/string-interner) A data structure to cache strings efficiently
- [`simple-interner`](https://crates.io/crates/simple-interner) A simple append-only interner
- [`string_cache`](https://crates.io/crates/string_cache) A string interning library for Rust, developed as part of the Servo project
    
## Just-in-time Compilation

- [`iced-x86`](https://crates.io/crates/iced-x86) A blazing fast and correct x86/x64 disassembler, assembler and instruction decoder
- [`masm-rs`](https://github.com/playxe/masm-rs) A JSC/SpiderMonkey like macro assembler
- [`jit`](https://crates.io/crates/jit) (LibJIT) Just-In-Time Compilation in Rust using LibJIT bindings
- [`lightning-sys`](https://crates.io/crates/lightning-sys) GNU lightning bindings for rust
- [`gccjit`](https://crates.io/crates/gccjit) Higher-level Rust bindings for libgccjit
- [`cranelift`](https://crates.io/crates/cranelift) Cranelift is a low-level retargetable code generator
  - [`cranelift-jit-demo`](https://github.com/bytecodealliance/cranelift-jit-demo) A JIT compiler and runtime for a toy language, using Cranelift 
- [`dynasm`](https://crates.io/crates/dynasm) A Dynamic assembler written in Rust for Rust

## Error reporting

- [`codespan-reporting`](https://crates.io/crates/codespan-reporting) Beautiful diagnostic reporting for text-based programming languages
- [`codespan`](https://crates.io/crates/codespan) Data structures for tracking locations in source code
- [`text-size`](https://crates.io/crates/text_size) A library that provides newtype wrappers for `u32` and `(u32, u32)` for use as text offsets
- [`ariadne`](https://crates.io/crates/ariadne) A fancy diagnostics & reporting crate
- [`miette`](https://crates.io/crates/miette) Fancy diagnostic reporting library and protocol for us mere mortals who aren't compiler hackers
    
## Language server protocol

- [`lsp-types`](https://crates.io/crates/lsp-types) Types for interaction with a language server, using VSCode's Language Server Protocol
- [`tower-lsp`](https://crates.io/crates/tower-lsp) Language Server Protocol implementation based on Tower
- [`codespan-lsp`](https://crates.io/crates/codespan-lsp) Conversions between codespan types and Language Server Protocol types
- [`lsp-server`](https://crates.io/crates/lsp-server) A generic LSP server scaffold
    
## Testing

- [`goldentests`](https://crates.io/crates/goldentests) A golden file testing library where tests can be configured within the same test file
- [`lang_tester`](https://crates.io/crates/lang_tester) Concise language testing framework for compilers and VMs (Linux only)
- [`libtest-mimic`](https://crates.io/crates/libtest-mimic) Dynamically construct a test-harness that looks and behaves like Rust's built-in test harness
- [`compiletest_rs`](https://crates.io/crates/compiletest_rs) The compiletest utility from the Rust compiler as a standalone testing harness
- [`insta`](https://crates.io/crates/insta) A snapshot testing library for Rust
- [`k9`](https://crates.io/crates/k9) Snapshot testing and better assertions
- [`bulk_examples_generator`](https://crates.io/crates/bulk_examples_generator) A tool created in Rust for create dozens/hundreds/thousands/millions of random examples based on a pest grammar (PEG)
    
## Unicode

- [`unicode-xid`](https://crates.io/crates/unicode-xid) Determine if a char is a valid identifier for a parser and/or lexer according to [Unicode Standard Annex #31](https://www.unicode.org/reports/tr31/) rules.
- [`unicode-normalisation`](https://crates.io/crates/unicode-normalization) Unicode character composition and decomposition utilities as described in [Unicode Standard Annex #15](http://www.unicode.org/reports/tr15/)
- [`unicode-segmentation`](https://crates.io/crates/unicode-segmentation) Iterators which split strings on Grapheme Cluster or Word boundaries, according to the [Unicode Standard Annex #29](http://www.unicode.org/reports/tr29/) rules
- [`unicode-width`](https://crates.io/crates/unicode-width) Determine displayed width of char and str types according to [Unicode Standard Annex #11](http://www.unicode.org/reports/tr11/) rules
- [`lexical-sort`](https://crates.io/crates/lexical-sort) Lexicographical sorting of unicode strings
    
## Incremental compilation

- [`salsa`](https://crates.io/crates/salsa) A generic framework for on-demand, incrementalized computation
    
## Floats/Ints/Bools

- [`lexical`](https://crates.io/crates/lexical) Lexical, to- and from-string conversion routines (Fast lexical conversion routines for both `std` and `no_std` environments)
- [`lexical-core`](https://crates.io/crates/lexical-core) Lexical, to- and from-string conversion routines (Low-level, lexical conversion routines for use in a `no_std` context)
- [`lexical_bool`](https://crates.io/crates/lexical_bool) A bool-like type that can be parsed from a string
- [`ryu`](https://crates.io/crates/ryu) A Rust implementation of the PLDI'18 paper [Ryū: fast float-to-string conversion](https://dl.acm.org/doi/10.1145/3192366.3192369) by Ulf Adams
- [`ryu-js`](https://crates.io/crates/ryu-js) Ryū-js is a fork of the ryu crate adjusted to comply to the ECMAScript number-to-string algorithm
- [`hexponent`](https://crates.io/crates/hexponent) C11 compliant hex float parsing
- [`ordered-float`](https://crates.io/crates/ordered-float) Total ordering on floats
- [`half`](https://crates.io/crates/half) A half-precision floating point `f16` type for Rust implementing the IEEE 754-2008 standard
- [`f128`](https://crates.io/crates/f128) Bindings to the gcc quadmath library
- [`approx`](https://crates.io/crates/approx) Approximate floating point equality comparisons and assertions
    
## Binary & object file parsing, generating and processing

- [`goblin`](https://crates.io/crates/goblin) An impish, cross-platform, ELF, Mach-o, and PE binary parsing and loading crate
- [`gimli`](https://crates.io/crates/gimli) A library for reading and writing the DWARF debugging format.
- [`faerie`](https://crates.io/crates/faerie) ELF and Mach-o native binary object file emitter
- [`object`](https://crates.io/crates/object) A unified interface for reading and writing object file formats.
- [`elf`](https://crates.io/crates/elf) A pure-rust library for parsing ELF files
- [`elfkit`](https://crates.io/crates/elfkit) An elf parser and manipulation library in pure rust 
    
## Symbolic Execution

- [`haybale`](https://crates.io/crates/haybale) Symbolic execution of LLVM IR
    
## Solvers

- [`rsmt2`](https://crates.io/crates/rsmt2) Wrapper for SMT-LIB 2 compliant SMT solvers.
- [`z3`](https://crates.io/crates/z3) A high-level rust bindings for the Z3 SMT solver from Microsoft Research
- [`z3-sys`](https://crates.io/crates/z3-sys) Low-level bindings for the Z3 SMT solver from Microsoft Research
- [`z3_ref`](https://crates.io/crates/z3_ref) A high level interface to the Z3 SMT solver
- [`z3d`](https://crates.io/crates/z3d) Z3 DSL interface for Rust
- [`boolector`](https://crates.io/crates/boolector) Safe high-level bindings for the Boolector SMT solver
- [`boolector-sys`](https://crates.io/crates/boolector-sys) Low-level bindings for the Boolector SMT solver
- [`smt2utils`](https://github.com/facebookincubator/smt2utils) Libraries and tools for the SMT-LIB-2 standard
  - [`smt2parser`](https://crates.io/crates/smt2parser) A generic parser for SMT2 commands, as specified by the SMT-LIB-2 standard
  - [`smt2proxy`](https://crates.io/crates/smt2proxy) An experimental binary tool to intercept and pre-process SMT2 commands before they are send to an SMT solver
  - [`z3tracer`](https://crates.io/crates/z3tracer) An experimental parser for Z3 tracing logs obtained by passing `trace=true proof=true` to Z3
- [`good_lp`](https://crates.io/crates/good_lp) Mixed Integer Linear Programming for Rust, with an user-friendly API. This crate allows modeling LP problems, and lets you solve them with various solvers.
- [Axiom Profiler](https://github.com/viperproject/axiom-profiler) A tool for visualising, analysing and understanding quantifier instantiations made via E-matching in a run of an SMT solver
- [[2017][PDF] Counterexample Guided Inductive Optimization based on Satisfiability Modulo Theories](https://ssvlab.github.io/lucasccordeiro/papers/jscp2017_2.pdf)

## CLI

- [`structopt`](https://crates.io/crates/structopt) Parse command line arguments by defining a struct
- [`clap`](https://crates.io/crates/clap) A simple to use, efficient, and full-featured Command Line Argument Parser 
- [`pico-args`](https://crates.io/crates/pico-args) An ultra simple CLI arguments parser
- [`argh`](https://crates.io/crates/argh) A derive-based argument parser optimized for code size

### Configuration

- [`etcetera`](https://crates.io/crates/etcetera) A library that aims to allow you to determine the locations of configuration, cache and data files for your application. Existing Rust libraries generally do not give you a choice in terms of which standards/conventions (Etcetera calls these ‘strategies’) they follow. Etcetera, on the other hand, gives you the choice
- [`toml`](https://crates.io/crates/toml) A TOML decoder and encoder for Rust (optionally uses [serde])
- [`envy`](https://crates.io/crates/envy) Deserialize environment variables into typesafe structs (uses [serde])
    
## Repl

- [`rustyline`](https://crates.io/crates/rustyline) Rustyline, a readline implementation based on Antirez's Linenoise
- [`repl-rs`](https://crates.io/crates/repl-rs) Library to generate a REPL for your application
- [`termwiz`](https://crates.io/crates/termwiz) Terminal Wizardry for Unix and Windows

## String handling

- [`beef`](https://crates.io/crates/beef) Faster, more compact implementation of [`Cow`](https://doc.rust-lang.org/alloc/borrow/enum.Cow.html).
- [`smol_str`](https://crates.io/crates/smol_str) Small-string optimized string type with O(1) clone
- [`smallstring`](https://crates.io/crates/smallstring) 'Small string' optimization: store small strings on the stack using smallvec
- [`heck`](https://crates.io/crates/heck) Heck is a case conversion library that exists to provide case conversion between common cases like CamelCase and snake_case. It is intended to be unicode aware, internally consistent, and reasonably well performing
- [`ropey`](https://crates.io/crates/ropey) Ropey is a utf8 text rope for Rust, designed to be the backing text-buffer for applications such as text editors. Ropey is fast, robust, and can handle huge texts and memory-incoherent edits with ease.

## Syntax trees

- [`rowan`](https://crates.io/crates/rowan) Generic lossless syntax trees
- [`cstree`](https://crates.io/crates/cstree) A fork of `rowan` with threadsafe syntax trees and built-in [source string interning](#string-interning)

## Pretty printing

- [`pretty`](https://crates.io/crates/pretty) Wadler-style pretty-printing combinators in Rust

## Variable binding

- [`moniker`](https://crates.io/crates/moniker) An automagical variable binding library for tracking variables in scopes

## Caching

- [`cached`](https://crates.io/crates/cached) Caching structures and simplified function memoization

## WASM

- [`wain`](https://crates.io/crates/wain) WebAssembly interpreter written in Safe Rust with zero dependencies
- [`wasmer`](https://crates.io/crates/wasmer) The high-level public API of the Wasmer WebAssembly runtime
- [`wasmtime`](https://crates.io/crates/wasmtime) High-level API to expose the Wasmtime runtime
- [`wasmtime-jit`](https://crates.io/crates/wasmtime-jit) JIT-style execution for WebAsssembly code in Cranelift
- [`wasmlite-parser`](https://crates.io/crates/wasmlite-parser) This crate parses WebAssembly modules and can generate LLVM IR based the data extracted from a module
- [`parity-wasm-cp`](https://crates.io/crates/parity-wasm-cp) WebAssembly binary format serialization/deserialization/interpreter
- [`substrate-wasm-builder`](https://crates.io/crates/substrate-wasm-builder) A utility for building WASM binaries
- [`walrus`](https://crates.io/crates/walrus) A library for performing WebAssembly transformations 

## Logging

- [`tracing`](https://crates.io/crates/tracing) Application-level tracing for Rust
  - [`tracing-timing`](https://crates.io/crates/tracing-timing) Inter-event timing metrics on top of `tracing`
  - [`tracing-coz`](https://crates.io/crates/tracing-coz) Rust-tracing support for the [coz](https://github.com/plasma-umass/coz/#installation) Causal Profiler
  - [`tracing-flame`](https://crates.io/crates/tracing-flame) A tracing `Layer` for generating a folded stack trace for generating flamegraphs and flamecharts with inferno
  - [`test-env-log`](https://crates.io/crates/test-env-log) A crate that takes care of automatically initializing logging and/or tracing for Rust tests.
  - [`tracing-unwrap`](https://crates.io/crates/tracing-unwrap) This crate provides `.unwrap_or_log()` and `.expect_or_log()` methods on `Result` and `Option` types that log failed unwraps to a `tracing::Subscriber`
- [`log`](https://crates.io/crates/log) A Rust library providing a lightweight logging facade
- [`slog`](https://crates.io/crates/slog) An ecosystem of reusable components for structured, extensible, composable and contextual logging for Rust

## Storage

- [`slotmap`](https://crates.io/crates/slotmap) Containers with persistent unique keys to access stored values: Insertion, deletion and access all take O(1) time with low overhead.
- [`indexmap`](https://crates.io/crates/indexmap) A hash table with consistent order and fast iteration
- [`vecmap`](https://crates.io/crates/vecmap) Vec-based Map and Set data structures

### Disjoint-sets

- [`union-find`](https://crates.io/crates/union-find) Struct and methods for union-find operation
- [`ena`](https://crates.io/crates/ena) An implementation of union-find in Rust; extracted from (and used by) rustc

## Incremental Analysis

- [`timely`](https://crates.io/crates/timely) A low-latency cyclic dataflow computational model, introduced in the paper [Naiad: a timely dataflow system](https://dl.acm.org/doi/10.1145/2517349.2522738)
  - [`differential-dataflow`](https://crates.io/crates/differential-dataflow) A data-parallel programming framework designed to efficiently process large volumes of data and to quickly respond to arbitrary changes in input collections, an implementation of [differential dataflow](https://github.com/timelydataflow/differential-dataflow/blob/master/differentialdataflow.pdf) over [timely dataflow](https://github.com/timelydataflow/timely-dataflow) on Rust.
  - [`dogsdogsdogs`](https://github.com/TimelyDataflow/differential-dataflow/tree/master/dogsdogsdogs) Worst-case optimal joins and delta queries in differential dataflow
  - [`dataflow-join`](https://github.com/frankmcsherry/dataflow-join) A streaming implementation of Ngo et al's `GenericJoin` in timely dataflow
  - [`timely-sort`](https://github.com/TimelyDataflow/timely-dataflow/tree/master/sort) An cache-aware implementation of radix sort in Rust
  - [`diagnostics`](https://github.com/TimelyDataflow/diagnostics) Diagnostic tools for [`timely-datafflow`](https://crates.io/crates/timely) and [`differential-dataflow`](https://crates.io/crates/differential-dataflow) computations
- [`differential-datalog`](https://github.com/vmware/differential-datalog) A programming language for incremental computation based on [`timely-dataflow`](https://crates.io/crates/timely) and [`differential-dataflow`](https://crates.io/crates/differential-dataflow), similar to [`IncA`](https://github.com/szabta89/IncA) or [`Souffle`](https://github.com/souffle-lang/souffle)

### Timely Dataflow Resources

- [Naiad: a timely dataflow system](https://dl.acm.org/doi/10.1145/2517349.2522738)
- [Timely Dataflow Book](https://timelydataflow.github.io/timely-dataflow/)
- [Differential Dataflow](https://github.com/timelydataflow/differential-dataflow/blob/master/differentialdataflow.pdf)
- [Differential Dataflow Book](https://timelydataflow.github.io/differential-dataflow/)
- Sudoku in Differential Dataflow: [blog](https://github.com/frankmcsherry/blog/blob/master/posts/2020-06-06.md#sudoku-in-differential-dataflow), [video series](https://www.youtube.com/watch?v=DR5V5bNpclg)
- An introduction to Timely Dataflow: [part 1](https://github.com/frankmcsherry/blog/blob/master/posts/2015-09-14.md), [part 2](https://github.com/frankmcsherry/blog/blob/master/posts/2015-09-18.md), [part 3](https://github.com/frankmcsherry/blog/blob/master/posts/2015-09-21.md)
- An introduction to Differential Dataflow: [part 1](https://github.com/frankmcsherry/blog/blob/master/posts/2015-09-29.md), [part 2](https://github.com/frankmcsherry/blog/blob/master/posts/2015-11-27.md)
- [Differential Dataflow meets Calculus](https://github.com/frankmcsherry/blog/blob/master/posts/2020-02-15.md)

## Fuzzing

- [`honggfuzz-rs`](https://crates.io/crates/honggfuzz) Honggfuzz is a security oriented fuzzer with powerful analysis options that supports evolutionary, feedback-driven fuzzing based on code coverage
- [`cargo-fuzz`](https://crates.io/crates/cargo-fuzz) A cargo subcommand for using libFuzzer
- [`libfuzzer-sys`](https://crates.io/crates/libfuzzer-sys) Barebones wrapper around LLVM's libFuzzer runtime library
- [`wasm-smith`](https://crates.io/crates/wasm-smith) A WebAssembly test case generator
- [`fuzzcheck`](https://crates.io/crates/fuzzcheck) A structure-aware coverage-guided fuzzer
- [`libafl`](https://crates.io/crates/libafl)

### Fuzzing Resources

- [Fuzzing a parser](https://arzg.github.io/lang/20/)
- [Rust Fuzz Book](https://rust-fuzz.github.io/book/cargo-fuzz.html)
- [Fuzzcheck guide](https://fuzzcheck.neocities.org/)
- [The Fuzzing Book](https://www.fuzzingbook.org/)
- [LibAFL guide](https://aflplus.plus/libafl-book/)

## Graphs

- [`egg`](https://crates.io/crates/egg) Egg is a flexible, high-performance e-graph library
  - [Herbie](https://github.com/uwplse/herbie)'s usage of `egg` to improve the accuracy of floating point calculations ([language](https://github.com/uwplse/herbie/blob/4adbd48b01b8a4c382af2bf60556b8be0fabcf70/egg-herbie/src/math.rs#L43-L66), [rules](https://github.com/uwplse/herbie/blob/4adbd48b01b8a4c382af2bf60556b8be0fabcf70/egg-herbie/src/rules.rs#L17-L934), [analysis](https://github.com/uwplse/herbie/blob/4adbd48b01b8a4c382af2bf60556b8be0fabcf70/egg-herbie/src/math.rs#L68-L196))
  - [Szalinski](https://github.com/uwplse/szalinski)'s usage of `egg` to simplify CAD programs ([language](https://github.com/uwplse/szalinski/blob/66dac92f8a77e7d77a604bc4fceee6590966d3ac/src/cad.rs#L55-L105), [rules](https://github.com/uwplse/szalinski/blob/08218dee8deb789d9de4cdaa2c83c276a0cca5fe/src/rules.rs#L43-L413), [appliers](https://github.com/uwplse/szalinski/blob/08218dee8deb789d9de4cdaa2c83c276a0cca5fe/src/rules.rs#L436-L899))
  - [Glenside](https://github.com/gussmith23/glenside)'s usage of `egg` for optimizing tensor programs ([language](https://github.com/gussmith23/glenside/blob/11a06375b9d91a7f66bddb2f16a8e866be8cd9c4/src/language/language.rs#L11-L296), [rules](https://github.com/gussmith23/glenside/blob/11a06375b9d91a7f66bddb2f16a8e866be8cd9c4/src/language/rewrites.rs), [analysis](https://github.com/gussmith23/glenside/blob/11a06375b9d91a7f66bddb2f16a8e866be8cd9c4/src/language/language.rs#L1066-L2982))
- [`petgraph`](https://crates.io/crates/petgraph) A graph data structure library. Provides graph types and graph algorithms
- [`timely`](https://crates.io/crates/timely) A low-latency cyclic dataflow computational model, introduced in the paper [Naiad: a timely dataflow system](https://dl.acm.org/doi/10.1145/2517349.2522738)
- [`differential-dataflow`](https://crates.io/crates/differential-dataflow) A data-parallel programming framework designed to efficiently process large volumes of data and to quickly respond to arbitrary changes in input collections, an implementation of [differential dataflow](https://github.com/timelydataflow/differential-dataflow/blob/master/differentialdataflow.pdf) over [timely dataflow](https://github.com/timelydataflow/timely-dataflow) on Rust.

## Type Checking

- [`rusttyc`](https://crates.io/crates/rusttyc) An interface that allows for an intuitive translation of inference rules based on a Hindney-Milner-like bounded type meet-semilattice into rust code
- [`polytype`](https://crates.io/crates/polytype) A Hindley-Milner polymorphic typing system

## Peephole Optimization

- [`egg`](https://crates.io/crates/egg) Egg is a flexible, high-performance e-graph library 
- [`peepmatic`](https://crates.io/crates/peepmatic) A DSL for peephole optimizations and compiler for generating peephole optimizers from them

## Garbage Collection

- [`broom`](https://crates.io/crates/broom) An ergonomic tracing garbage collector that supports mark 'n sweep garbage collection
- [`gc`](https://crates.io/crates/gc) A simple tracing (mark and sweep) garbage collector for Rust
- [`shredder`](https://crates.io/crates/shredder) Garbage collection as a library for Rust
- [`comet`](https://crates.io/crates/comet-gc) A garbage collection library for implementing VMs in Rust

## Guides & Resources

- [Making a language in Rust](https://arzg.github.io/lang/) A series about making a programming language called Eldiro using the Rust programming language
- [Crafting Interpreters](https://craftinginterpreters.com/welcome.html) Implementing everything from parsing to garbage collection to bytecode VMs, highly reccomended as an introduction to language development ([Homepage](https://craftinginterpreters.com))
- [Create Your Own Programming Language with Rust](https://createlang.rs/)
- [Where to Start Hand-Writing a Parser (in Rust)](https://domenicquirl.github.io/blog/parsing-basics/)
- [Writing a simple parser in Rust](https://adriann.github.io/rust_parser.html)
- GC and Rust [part 0](http://blog.pnkfx.org/blog/2015/10/27/gc-and-rust-part-0-how-does-gc-work/), [part 1](http://blog.pnkfx.org/blog/2015/11/10/gc-and-rust-part-1-specing-the-problem/) and [part 2](http://blog.pnkfx.org/blog/2016/01/01/gc-and-rust-part-2-roots-of-the-problem/)
- Matklad on pratt parsing: [Simple but Powerful Pratt Parsing](https://matklad.github.io/2020/04/13/simple-but-powerful-pratt-parsing.html) and [From Pratt to Dikjstra](https://matklad.github.io/2020/04/15/from-pratt-to-dijkstra.html)
- [Pure AST based linting sucks](https://rdambrosio016.github.io/rust/2020/09/18/pure-ast-based-linting-sucks.html)
- [LLVM's Kaleidoscope in Rust](https://github.com/jauhien/iron-kaleidoscope) The Kaleidoscope Language tutorial, showing how to implement a simple language using LLVM in Rust
- [Where to Start Hand-Writing a Parser (in Rust) ](https://domenicquirl.github.io/blog/parsing-basics/) An introduction to programming language parsing in which we hand-write a parser and run it on some real input
- [x86 and amd64 instruction reference](https://www.felixcloutier.com/x86/)
- [X86 Opcode and Instruction Reference](http://ref.x86asm.net/index.html)
- [Linear Scan Register Allocation on SSA Form](https://c9x.me/compile/bib/Wimmer10a.pdf)
- [A bibliography of papers related to symbolic execution](https://github.com/saswatanand/symexbib)
- [Instruction Latencies, Throughput and Micro-Operation Breakdowns for Intel, AMD and VIA CPUs](https://www.agner.org/optimize/instruction_tables.pdf)
- [[1995][PDF] Symbolic Range Propagation](https://citeseerx.ist.psu.edu/viewdoc/summary?doi=10.1.1.30.4717)
- [[2001][PDF] Efficient Symbolic Analysis for Optimizing Compilers](https://www.cs.fsu.edu/~engelen/cc01.pdf)
- [[2021][Video] A New Approach to Removing Redundant Conditions in LLVM](https://www.youtube.com/watch?v=1hm5ZVmBEvo)
- [[2017][Video] Polyhedral Value & Memory Analysis](https://www.youtube.com/watch?v=xSA0XLYJ-G0)
- [Simplify: A Theorem Prover for Program Checking](https://www.hpl.hp.com/techreports/2003/HPL-2003-148.pdf)
- [Elegant and performant recursion in Rust](https://recursion.wtf/posts/rust_schemes/)

### Type Checking

- [Type Checking in less than 100 lines of Rust](https://play.rust-lang.org/?version=stable&mode=debug&edition=2018&gist=a15a24394c145e4e02afa3b48bb51ea1) (Credit to [@zesterer](https://github.com/zesterer))
- [Bidirectional Type Checking in ~200 lines of OCaml](https://gist.github.com/mb64/87ac275c327ea923a8d587df7863d8c7) (Written in OCaml, credit to [@mb64](https://github.com/mb64))
- [[2020][PDF] Complete and Easy Bidirectional Typechecking for Higher-Rank Polymorphism](https://arxiv.org/abs/1306.6032)
- [Implementation of "Complete and Easy Bidirectional Typechecking for Higher-Rank Polymorphism"](https://github.com/segeljakt/BidirectionalTypechecking) (Written in Rust, from [@segeljakt](https://github.com/segeljakt))
- [Implementation of "Complete and Easy Bidirectional Typechecking for Higher-Rank Polymorphism"](https://github.com/JDemler/BidirectionalTypechecking) (Written in Rust, from [@JDemler](https://github.com/JDemler))
- [A bidirectional type inference system loosely based on Complete and Easy Bidirectional Typechecking for Higher-Rank Polymorphism.](https://github.com/samuela/bidirectional-typing) (Written in Haskell)
- [Didactic implementation of the type checker described in "Complete and Easy Bidirectional Typechecking for Higher-Rank Polymorphism"](https://github.com/soren-n/bidi-higher-rank-poly) (Written in OCaml)
- [An implementation of a predicative polymorphic language with bidirectional type inference and algebraic data types](https://github.com/zehaochen19/vanilla-lang) (Written in Haskell)

### Inlining

- [Inlining Decisions in Visual Studio](https://devblogs.microsoft.com/cppblog/inlining-decisions-in-visual-studio/)
- [C++ Inliner Improvements: The Zipliner](https://devblogs.microsoft.com/cppblog/c-inliner-improvements-the-zipliner/)
- [John Carmack on Inlined Code](https://collincode.wordpress.com/2016/07/19/john-carmack-on-inlined-code/)
- [How RyuJIT inlines a function (heuristics)](https://web.archive.org/web/20210517175814/https://egorbo.com/how-inlining-works.html)
- [Smarter C/C++ inlining with attribute((flatten))](https://awesomekling.github.io/Smarter-C++-inlining-with-attribute-flatten/)
- [Do compilers take inline as a hint?](https://blog.tartanllama.xyz/inline-hints/)
- [cmd/compile: improve inlining cost model](https://github.com/golang/go/issues/17566)
- [What does 'inline' mean?](https://forum.dlang.org/thread/mailman.3723.1591596899.31109.digitalmars-d@puremagic.com)
- [Zebu VM check_should_inline_func()](https://gitlab.anu.edu.au/mu/mu-impl-fast/-/blob/6572fe39ae65e424bdaf612f461fe60c8fc0b95f/src/compiler/passes/inlining.rs#L89)
- [Warp: Improved JS performance in Firefox 83](https://hacks.mozilla.org/2020/11/warp-improved-js-performance-in-firefox-83/)
- [When Short Methods Pay Off: JIT Inlining](https://dzone.com/articles/jit-inlining)
- [cross-module inlining in guile -- wingolog](https://wingolog.org/archives/2021/05/13/cross-module-inlining-in-guile)
- [Inline In Rust](https://matklad.github.io//2021/07/09/inline-in-rust.html)
- [It’s Not Always iCache](https://matklad.github.io/2021/07/10/its-not-always-icache.html)
- [[2003][PDF] Adaptive Online Context-Sensitive Inlining](http://www.cs.cmu.edu/afs/cs/academic/class/15745-s07/www/papers/hazelwood-cgo03.pdf)
- [[2003][PDF] To Inline or Not to Inline. Enhanced Inlining Decisions](https://citeseerx.ist.psu.edu/viewdoc/download?doi=10.1.1.6.946&rep=rep1&type=pdf)
- [[2004][PDF] Fast and Effective Procedure Inlining](https://guenchi.github.io/Scheme/doc/Fast%20and%20Effective%20Procedure%20Inlining.pdf)
- [[2016][PDF] CSE P 501 - Compilers. Inlining and Devirtualization](https://courses.cs.washington.edu/courses/csep501/18sp/lectures/X1-inlining.pdf)
- [[2017][PDF] TurboFan Inlining Heuristics](https://docs.google.com/document/d/1VoYBhpDhJC4VlqMXCKvae-8IGuheBGxy32EOgC2LnT8/edit)
- [[2019][PDF] Guiding Inlining Decisions Using Post-Inlining Transformations](https://webdocs.cs.ualberta.ca/~amaral/thesis/ErickOchoaMSc.pdf)
- [[2019][PDF] An Optimization-Driven Incremental Inline Substitution Algorithm for Just-in-Time Compilers](http://aleksandar-prokopec.com/resources/docs/prio-inliner-final.pdf)
- [[2021][PDF] Inlining for Code Size Reduction](https://homepages.dcc.ufmg.br/~fernando/publications/papers/SBLP21Pacheco.pdf)

### RVSDG

- [[2020][PDF] RVSDG: An Intermediate Representation for Optimizing Compilers](https://www.sjalander.com/research/pdf/sjalander-tecs2020.pdf)
- [[2018][PDF] RVSDG: An Intermediate Representation for the Multi-Core Era](https://www.sjalander.com/research/pdf/sjalander-mcc2018.pdf)
- [[2015][PDF] Perfect Reconstructability of Control Flow from Demand Dependence Graphs](https://dl.acm.org/doi/10.1145/2693261)
- [Principles, Techniques, and Tools for Explicit and Automatic Parallelization](https://www.researchgate.net/publication/332241231_Principles_Techniques_and_Tools_for_Explicit_and_Automatic_Parallelization)
- [[Slides] Compiling with the Regionalized Value State Dependence Graph](https://www.sintef.no/contentassets/11da6d67207348db98a30ddbdf3b0bba/reissmann_poster.pdf)
- [JLM RVSDG Implementation (C++)](https://github.com/phate/jlm)
- [JIVE RVSDG Graph Implementation (C++)](https://github.com/phate/jive/tree/master)
- [RVSDG Viewer (C++)](https://github.com/phate/rvsdg-viewer)
- [Cranial Coitus RVSDG Brainfuck Optimizer (Rust)](https://github.com/Kixiron/cranial-coitus)
- [[2018][PDF] Semantic Reasoning About the Sea of Nodes](https://hal.inria.fr/hal-01723236/file/sea-of-nodes-hal.pdf)

### Equality Saturation

- [[2010][PDF] Equality Saturation: A New Approach to Optimization](https://arxiv.org/abs/1012.1802)
- [[2020][PDF] egg: Fast and Extensible Equality Saturation](https://arxiv.org/abs/2004.03082)
- [[2021][PDF] Rewrite Rule Inference Using Equality Saturation](https://arxiv.org/abs/2108.10436)
- [[2021][PDF] Sketch-Guided Equality Saturation: Scaling Equality Saturation to Complex Optimizations in Languages with Bindings](https://arxiv.org/abs/2111.13040)
- [[2021][PDF] Caviar: An E-graph Based TRS for Automatic Code Optimization](https://arxiv.org/abs/2111.12116)
- [[2002][PDF] SPORES: Sum-Product Optimization via Relational Equality Saturation for Large Scale Linear Algebra](https://arxiv.org/abs/2002.07951)
- [[2021][PDF] Relational E-Matching](https://arxiv.org/abs/2108.02290)
- [[2021][PDF] Rewrite Rule Inference Using Equality Saturation](https://arxiv.org/abs/2108.10436)

[serde]: https://crates.io/crates/serde
