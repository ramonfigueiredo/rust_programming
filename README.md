Some programming examples in Rust
===========================

## Contents
1. [Rust Programming Language](#rust-programming-language)
2. [Installing Rust](#installing-rust)
3. [Cargo-The Rust build tool and package manager](#cargo-the-rust-build-tool-and-package-manager)
4. [Generating a new Rust project](#generating-a-new-rust-project)
5. [Adding Rust dependencies](#adding-rust-dependencies)
6. [Data Types](#data-types)
7. [Variables](#variables)
8. [Constant](#constant)
9. [String](#string)
10. [Operators](#operators)
11. [Decision Making](#decision-making)
12. [Loop](#loop)
13. [Functions](#functions)
14. [Tuple](#tuple)
15. [Array](#array)
16. [Ownership](#ownership)
17. [Borrowing](#borrowing)
18. [Slices](#slices)
19. [Structure](#structure)
20. [Enums](#enums)
21. [Modules](#modules)
22. [Collections](#collections)
23. [Error Handling](#error-handling)
24. [Generic Types](#generic-types)
25. [Input Output](#input-output)
26. [File Input/ Output](#file-Input-and-output)
27. [Package Manager](#package-manager)
28. [Iterator and Closure](#iterator-and-closure)
29. [Smart Pointers](#smart-pointers)
30. [Concurrency](#concurrency)

## Rust Programming Language

The [Rust programming language](https://www.rust-lang.org/) is a multi-paradigm, high-level, general-purpose programming language. Rust is popular for systems programming but also offers high-level features including some functional programming constructs. Rust runs really fast like C and C++, prevents almost all crashes, and eliminates data races. Rust is intended to be a language for highly concurrent and highly secure systems.

Graydon Hoare (a software developer) created Rust as a personal project while working at Mozilla Research in 2006. Mozilla officially sponsored the project in 2009. Since the first stable release in May 2015, Rust has been adopted by companies including Amazon, Discord, Dropbox, Facebook (Meta), Google (Alphabet), and Microsoft. In 2022, Rust became the third programming language used in the Linux kernel, after C and Assembly language.

### Application versus Systems Programming Languages

Application programming languages like Java or C# are used to build software, which provide services to the user directly. They help us build business applications like spreadsheets, word processors, web applications or mobile applications.

Systems programming languages like Rust, C, and C++ are used to build software and software platforms. They can be used to build operating systems, game engines, compilers, etc. These programming languages require a great degree of hardware interaction.

Systems and application programming languages face two major problems:
- It is difficult to write secure code.
- It is difficult to write multi-threaded code.

### Rust

Rust focuses on three goals: 1) safety, 2) speed, 3) concurrency.

The Rust language was designed for developing highly reliable and fast software in a simple way. Rust can be used to write high-level programs down to hardware-specific programs.

**Performance:** Rust programming language does not have a Garbage Collector (GC) by design. This improves the performance at runtime.

**Memory safety at compile time:** Software built using Rust is safe from memory issues like dangling pointers, buffer overruns and memory leaks.

**Multi-threaded applications:** Rust's ownership and memory safety rules provide concurrency without data races.

**Support for Web Assembly (WASM):** Web Assembly helps to execute high computation intensive algorithms in the browser, on embedded devices, or anywhere else. It runs at the speed of native code. Rust can be compiled to Web Assembly for fast, reliable execution.

**Note:** Rustaceans are people who use Rust, contribute to Rust, or are interested in the development of Rust.


* [Getting started with Rust](https://www.rust-lang.org/learn/get-started): Quickly set up a Rust development environment and write a small app.
* [Rust playground](https://play.rust-lang.org/): A browser interface to the Rust compiler to experiment with the language.
* [The Rust programming language's official book](https://doc.rust-lang.org/book/)

Go back to [Contents](#contents).

## Installing Rust

To download Rustup and install Rust on Linux, macOS, or another Unix-like OS, run the following in your terminal, then follow the on-screen instructions.

```
curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh
```

The installation script automatically adds Rust to your system PATH after your next login. 
To start using Rust right away instead of restarting your terminal, run the following command in your terminal to add Rust to your system PATH manually.

```
source $HOME/.cargo/env
```

Alternatively, you can add the following line to your ~/.bash_profile −

```
export PATH="$HOME/.cargo/bin:$PATH"
```

See [Other Installation Methods](https://forge.rust-lang.org/infra/other-installation-methods.html) if you are on Windows.

Rust updates very frequently. If you have installed Rustup some time ago, chances are your Rust version is out of date. Get the latest version of Rust by running ```rustup update```.

Go back to [Contents](#contents).

## Cargo-The Rust build tool and package manager

Cargo is the Rust build tool and package manager. When you install Rustup you'll also get the latest stable version of the Rust build tool and package manager, also known as ```Cargo```. 

Cargo does lots of things:

* Build your project with ```cargo build```
* Run your project with ```cargo run```
* Test your project with ```cargo test```
* Build documentation for your project with ```cargo doc```
* Publish a library to [crates.io](https://crates.io/) with ```cargo publish```

To test that you have Rust and Cargo installed, you can run this in your terminal of choice:

```
cargo --version
```

Go back to [Contents](#contents).

## Generating a new Rust project

To use ```Cargo``` to make a new project, run the following in your terminal:

```
cargo new your-project-name
```

where ```your-project-name``` is the name of your Rust project.

This will generate a new directory called ```your-project-name``` with the following files:

```
your-project-name/
├── Cargo.toml
└── src
    └── main.rs
```

* **Cargo.toml** is the manifest file for Rust. It's where you keep metadata for your project, as well as dependencies.
* **src/main.rs** is where you write your application code.

Commands:

** ```cargo new``` generates a "Hello, world!" project for us! 

To execute a Rust program, run the following in your terminal:

```
cargo run
```

You should see this in your terminal:

```
> cargo run --color=always
    Finished dev [unoptimized + debuginfo] target(s) in 0.00s
     Running `target/debug/rust_tutorial`
Hello, world!

Process finished with exit code 0
```

Go back to [Contents](#contents).

## Adding Rust dependencies

In Rust, we often refer to packages as "crates". The package registry for Rust is available on [crates.io](https://crates.io/).

To add a dependency to your Rust application, change the ```Cargo.toml``` file.

For example, you can use a crate called ```ferris-says```.

In your ```Cargo.toml``` file, add this information:

```
[dependencies]
ferris-says = "0.2"
```

Now we can run:

```
cargo build
```

...and ```Cargo``` will install the dependency.

By running the command above created, ```cargo``` creates a new file: Cargo.lock.

* **Cargo.lock**: This file is a log of the exact versions of the dependencies we are using locally.

To use this dependency, open main.rs and use the ```use ferris_says::say;```:

This line means that we can now use the ```say``` function that the ```ferris-says``` crate exports.

Code example using ```ferris-says```.

```
use ferris_says::say;
use std::io::{stdout, BufWriter};

fn main() {
    let stdout = stdout();
    let message = String::from("Hello fellow Rustaceans!");
    let width = message.chars().count();

    let mut writer = BufWriter::new(stdout.lock());
    say(message.as_bytes(), width, &mut writer).unwrap();
}
```

To run the Rust application, type:

```
cargo run
```

Output:

```
$ cargo run
    Finished dev [unoptimized + debuginfo] target(s) in 0.00s
     Running `target/debug/rust_programming`
 __________________________
< Hello fellow Rustaceans! >
 --------------------------
        \
         \
            _~^~^~_
        \) /  o o  \ (/
          '_   -   _'
          / '-----' \
```

**Note:** [Ferris](https://rustacean.net/) is a crab and is an unofficial mascot for Rust. Ferris is a name playing off of the adjective, “ferrous,” meaning of or pertaining to iron.


Go back to [Contents](#contents).

## Data Types

Go back to [Contents](#contents).

## Variables

Go back to [Contents](#contents).

## Constant

Go back to [Contents](#contents).

## String

Go back to [Contents](#contents).

## Operators

Go back to [Contents](#contents).

## Decision Making

Go back to [Contents](#contents).

## Loop

Go back to [Contents](#contents).

## Functions

Go back to [Contents](#contents).

## Tuple

Go back to [Contents](#contents).

## Array

Go back to [Contents](#contents).

## Ownership

Go back to [Contents](#contents).

## Borrowing

Go back to [Contents](#contents).

## Slices

Go back to [Contents](#contents).

## Structure

Go back to [Contents](#contents).

## Enums

Go back to [Contents](#contents).

## Modules

Go back to [Contents](#contents).

## Collections

Go back to [Contents](#contents).

## Error Handling

Go back to [Contents](#contents).

## Generic Types

Go back to [Contents](#contents).

## Input Output

Go back to [Contents](#contents).

## File Input and Output

Go back to [Contents](#contents).

## Package Manager

Go back to [Contents](#contents).

## Iterator and Closure

Go back to [Contents](#contents).

## Smart Pointers

Go back to [Contents](#contents).

## Concurrency

Go back to [Contents](#contents).