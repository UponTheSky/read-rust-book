# Programming a Guessing Game

## Setting Up a New Project, Processing a Guess
- `std::io` library: for input/output
- stdlib and `use`
  - by default, Rust has items defined in the stdlib that it brings into the scope of every program
  - called "prelude"
  - if the type you want is not in prelude, you have to import it via `use` == `using` in C++

### Storing Values with Variables
- in rust, variables are immutable by default
  - to make it mutable, just attach `mut`

- `String` is a string type provided by the stdlib that is growable

- `::`: *associated*
  - an **associated** function is a function that's implemented on a type
  - `String::new` is an associated function that creates an empty string

### Receiving User Input
- `std::io::stdin`: returns an instance of `std::io::Stdin`
  - this type represents a handle to the standard input for your terminal

- `std::io::Stdin::read_line`

- `&`: reference, immutable by default
  - gives a way to let multiple parts of your code access one piece of data without needing to copy that data into memory multiple times
  - `&mut guess`: make reference to `guess` mutable

### Handling Potential Failure with Result
- `std::result::Result` => enum, and each state is called a *variant*
  - `Ok`: the operation was successful => the successfully generated value is inside `Ok`
  - `Err`: the operation failed => `Err` contains the information about how, and why the operation failed

- `expect`: error handling logic inside `Result` type

### Printing Values with println! Placeholders
- string interpolation

## Generating a Secret Number
- using `rand` crate

### Using a Crate to Get More Functionality
- a **crate** is a collection of Rust source code files
  - *binary crate*: executable by itself
  - *library crate*: intended to be used in other programs, and can't be executed on its own

- `Cargo.toml`'s `[dependencies]`
  - external crates your project depends on with their versions
  - 0.8.5 = ^0.8.5(=after 0.8.5, buy before 0.9.x)
  - `crates.io`
    - Cargo fetches the latest versions of everything that dependency needs from the *registry*
    - registry is a copy of data from `Crates.io`
    - `Crates.io`: the place where people in the Rust ecosystem post their open source Rust projects

  - after updating the registry, Cargo checks `[dependencies]` section, and downloads any crates listed that aren't already downloaded
  - after downloading the crates, Rust compiles them and then compiles the project with the dependencies available

- Rust knows what has been changed or not: you don't need to compile from the beginning for every compilation

#### Ensuring Reproducible Builds with the Cargo.lock File
- `Cargo.lock`: you can rebuild the same artifact every time you or anyone else builds your code
  - Cargo will use only the versions of the dependencies you specified until you indicate otherwise

- when you build a project
  - for the first time: Cargo figures out all the versions of the dependencies that fit the criteria and then writes them to the `Cargo.lock`
  - in the future: Cargo will first check `Cargo.lock` and will use the versions specified there(reproducible code)

#### Updating a Crate to Get a New Version
- `cargo update`
  - ignores `Cargo.lock`, and figures out all the latest versions that fit your `Cargo.toml` specifications
  - and then Cargo rewrite those versions to `Cargo.lock`

### Generating a Random Number
- `Rng`: a trait that defines methods that random number generators implement
  - this trait must be in scope for us to use those methods

## Comparing the Guess to the Secret Number
- `Ordering`: enum
- `match`: kind of `switch...case`
  - *arm*: each different case
  - no fall through

- type system: integer default is `i32`

- shadowing variables is allowed in Rust
- parsing the text values:
  - `trim()`: getting rid of whitespaces
  - `parse()`: converting a string variable into another type
  - since `parse` could cause possible errors, we have `expect` here as well

## Allowing Multiple Guesses with Looping
- `loop`: an infinite loop

### Quitting After a Correct Guess
- `break`

### Handling Invalid Input
- again, `match` pattern
