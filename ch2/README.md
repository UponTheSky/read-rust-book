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
