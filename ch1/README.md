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
