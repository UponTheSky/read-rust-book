# https://doc.rust-lang.org/book/ch01-00-getting-started.html

# Installation
- *linker*: a program to join compiled outputs into one file
  - Rust uses C compiler
  - some common Rust packages depend on C code and will need a C compile

# Hello, World!

## Anatomy of a Rust Program
- `main` function
  - a special function: always the first code that runs in every executable Rust program

- `rustfmt`: formatting(see appendix d: https://doc.rust-lang.org/book/appendix-04-useful-development-tools.html)

- `println!(str)'`
  - `!` is calling a macro, rather than a function(a function is normally without `!`)
  - `;`: semicolon is required

## Compiling and Running Are Separate Steps
- before running a Rust program, you must compile it using the Rust compiler `rustc`
  - the compiler produces a binary file that is executable

- as the project grows bigger, you want to separate a chunk of functionalities => Cargo


# Hello, Cargo!
- **Cargo**: Rust's build system and package manager
  - Cargo builds your code
  - Cargo downnloads and builds the dependencies you need

## Creating a Project with Cargo
- `cargo new <project_name>`
  - `cargo.toml`, `src/main.rs`, (and optionally) `.git`

- `cargo.toml`
  - `[package]`, `[dependencies]`
  - in Rust, one single package is called "crate"

- project file structure
  - top: `cargo.toml`, README, LICENSE, and anything else not related to the code
## Building and Running a Cargo Project
- `cargo build` in the root directory(where `cargo.toml` is located in)
  - default: debug file
  - automatically generating and managing `cargo.lock`: keeps track of the exact versions of the dependencies in your project

- `cargo run` = `cargo build` + `./<executable binary file>`
- `cargo check`: make sure that the code compiles, but doesn't produce an executable
  - way faster than `cargo build`

## Building for Release
- `cargo build --release`: compile the project code with optimizations
- build file in `target/release` instead of `target/debug`
- slower in build, but faster in execution

## Cargo as Convention

