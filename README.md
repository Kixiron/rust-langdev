# Langdev libraries for Rust

- [Lexers](#lexers)
- [Parsers](#parsers)
- [Codegen](#codegen)
- [String interning](#string-interning)
- [Just-in-time compilation](#just-in-time-compilation)
- [Error reporting](#error-reporting)
- [Language server protocol](#langauge-server-protocol)
- [Testing](#testing)
- [Incremental compilation](#incremental-compilation)
- [Floats/Ints/Bools](#floats-ints-bools)
- [Binary & object file parsing, generating and processing](#binary-object-file-parsing-generating-and-processing)
- [Solvers](#solvers)
- [CLI](#cli)
- [Repl](#repl)
- [String handling](#string-handling)
- [Syntax trees](#syntax-trees)
- [Pretty printing](#pretty-printing)

## Lexers

- [`logos`](https://crates.io/crates/logos) Logos has two goals: To make it easy to create a Lexer, so you can focus on more complex problems and to make the generated Lexer faster than anything you'd write by hand
    
## Parsers

- [`parze`](https://crates.io/crates/parze) Parze is a clean, efficient parser combinator written in Rust
- [`lalrpop`](https://crates.io/crates/lalrpop) A convenient LR(1) parser generator
- [`nom`](https://crates.io/crates/nom) A byte-oriented, zero-copy, parser combinators library
- [`combine`](https://crates.io/crates/combine) Fast parser combinators on arbitrary streams with zero-copy support.
- [`pom`](https://crates.io/crates/pom) PEG parser combinators using operator overloading without macros.
- [`peg`](https://crates.io/crates/peg) A simple Parsing Expression Grammar (PEG) parser generator.
- [`glue`](https://crates.io/crates/glue) Glue is a parser combinator framework for parsing text based formats, it is easy to use and relatively fast too
- [`pratt`](https://crates.io/crates/pratt) A general purpose pratt parser for Rust
- [`pest`](https://crates.io/crates/pest) A general purpose parser written in Rust with a focus on accessibility, correctness, and performance using parsing expression grammars (PEG)
    
## Codegen

- [`cranelift`](https://crates.io/crates/cranelift)
- [`llvm-sys`](https://crates.io/crates/llvm-sys)
- [`llama`](https://crates.io/crates/llama)
- [`inkwell`](https://crates.io/crates/inkwell)
- [`llvm-ir`](https://crates.io/crates/llvm-ir)
- [`llvmenv`](https://crates.io/crates/llvmenv)
    
## String interning

- [`lasso`](https://crates.io/crates/lasso) A multithreaded and single threaded string interner with a minimal memory footprint and arena allocation
- [`string-interner`](https://crates.io/crates/string-interner) A data structure to cache strings efficiently
- [`simple-interner`](https://crates.io/crates/simple-interner) A simple append-only interner
- [`string_cache`](https://crates.io/crates/string_cache) A string interning library for Rust, developed as part of the Servo project
    
## Just-in-time Compilation

- [`masm-rs`](https://github.com/playxe/masm-rs)
- [`jit`](https://crates.io/crates/jit) (LibJIT)
- [`lightning-sys`](https://crates.io/crates/lightning-sys)
- [`gccjit`](https://crates.io/crates/gccjit)
- [`cranelift`](https://crates.io/crates/cranelift)
    
## Error reporting

- [`codespan-reporting`](https://crates.io/crates/codespan-reporting) Beautiful diagnostic reporting for text-based programming languages
- [`codespan`](https://crates.io/crates/codespan) Data structures for tracking locations in source code
    
## Language server protocol

- [`lsp-types`](https://crates.io/crates/lsp-types)
- [`tower-lsp`](https://crates.io/crates/tower-lsp)
- [`codespan-lsp`](https://crates.io/crates/codespan-lsp)
- [`lsp-server`](https://crates.io/crates/lsp-server)
    
## Testing

- [`goldentests`](https://crates.io/crates/goldentests) A golden file testing library where tests can be configured within the same test file
- [`lang_tester`](https://crates.io/crates/lang_tester) Concise language testing framework for compilers and VMs (Linux only)
- [`compiletest_rs`](https://crates.io/crates/compiletest_rs) The compiletest utility from the Rust compiler as a standalone testing harness
    
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
- [`hexponent`](https://crates.io/crates/hexponent) C11 compliant hex float parsing
- [`ordered-float`](https://crates.io/crates/ordered-float) Total ordering on floats
    
## Binary & object file parsing, generating and processing

- [`goblin`](https://crates.io/crates/goblin)
- [`gimli`](https://crates.io/crates/gimli)
- [`faerie`](https://crates.io/crates/faerie)
- [`object`](https://crates.io/crates/object)
- [`elf`](https://crates.io/crates/elf)
- [`elfkit`](https://crates.io/crates/elfkit)
    
## Symbolic Execution

- [`haybale`](https://crates.io/crates/haybale) Symbolic execution of LLVM IR
    
## Solvers

- [`z3`](https://crates.io/crates/z3)
- [`z3-sys`](https://crates.io/crates/z3-sys)
- [`z3_ref`](https://crates.io/crates/z3_ref)
- [`z3d`](https://crates.io/crates/z3d)
- [`boolector`](https://crates.io/crates/boolector)
- [`boolector-sys`](https://crates.io/crates/boolector-sys)

## CLI

- [`structopt`](https://crates.io/crates/structopt)
- [`clap`](https://crates.io/crates/clap)
- [`pico-args`](https://crates.io/crates/pico-args)
- [`argh`](https://crates.io/crates/argh)
    
## Repl

- [`rustyline`](https://crates.io/crates/rustyline) Rustyline, a readline implementation based on Antirez's Linenoise
- [`repl-rs`](https://crates.io/crates/repl-rs) Library to generate a REPL for your application
- [`termwiz`](https://crates.io/crates/termwizs) Terminal Wizardry for Unix and Windows

## String handling

- [`beef`](https://crates.io/crates/beef) Faster, more compact implementation of [`Cow`](https://doc.rust-lang.org/alloc/borrow/enum.Cow.html).
- [`smol_str`](https://crates.io/crates/smol_str) Small-string optimized string type with O(1) clone
- [`smallstring`](https://crates.io/crates/smallstring) 'Small string' optimization: store small strings on the stack using smallvec

## Syntax trees

- [`rowan`](https://crates.io/crates/rowan) Generic lossless syntax trees

## Pretty printing

- [`pretty`](https://crates.io/crates/pretty) Wadler-style pretty-printing combinators in Rust
    
