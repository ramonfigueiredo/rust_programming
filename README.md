Some programming examples in Rust
===========================

## Contents
1. [Rust Programming Language](#rust-programming-language)
1. [Installing Rust](#installing-rust)
1. [Cargo. The Rust build tool and package manager](#cargo.-the-rust-build-tool-and-package-manager)
1. [Data Types](#data-types)
2. [Variables](#variables)
3. [Constant](#constant)
4. [String](#string)
5. [Operators](#operators)
6. [Decision Making](#decision-making)
7. [Loop](#loop)
8. [Functions](#functions)
9. [Tuple](#tuple)
10. [Array](#array)
11. [Ownership](#ownership)
12. [Borrowing](#borrowing)
13. [Slices](#slices)
14. [Structure](#structure)
15. [Enums](#enums)
16. [Modules](#modules)
17. [Collections](#collections)
18. [Error Handling](#error-handling)
19. [Generic Types](#generic-types)
20. [Input Output](#input-output)
21. [File Input/ Output](#file-Input-and-output)
22. [Package Manager](#package-manager)
23. [Iterator and Closure](#iterator-and-closure)
24. [Smart Pointers](#smart-pointers)
25. [Concurrency](#concurrency)

## Rust Programming Language

The [Rust programming language](https://www.rust-lang.org/) is a multi-paradigm, high-level, general-purpose programming language. Rust is popular for systems programming but also offers high-level features including some functional programming constructs.

* Rust emphasizes performance, type safety, and concurrency. 
	* Rust enforces memory safety (all references point to valid memory) without requiring the use of a garbage collector or reference counting present in other memory (safe languages).
	* To simultaneously enforce memory safety and prevent concurrent data races, Rust's "borrow checker" tracks the object lifetime of all references in a program during compilation. 

Software developer Graydon Hoare created Rust as a personal project while working at Mozilla Research in 2006. Mozilla officially sponsored the project in 2009. Since the first stable release in May 2015, Rust has been adopted by companies including Amazon, Discord, Dropbox, Facebook (Meta), Google (Alphabet), and Microsoft. In 2022, Rust became the third programming language used in the Linux kernel, after C and Assembly language.

* [Getting started with Rust](https://www.rust-lang.org/learn/get-started): Quickly set up a Rust development environment and write a small app.
* [The Rust programming language's official book](https://doc.rust-lang.org/book/)

Go back to [Contents](#contents).

## Installing Rust

To download Rustup and install Rust on Linux, macOS, or another Unix-like OS, run the following in your terminal, then follow the on-screen instructions.

```
curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh
```

See [Other Installation Methods](https://forge.rust-lang.org/infra/other-installation-methods.html) if you are on Windows.

Rust updates very frequently. If you have installed Rustup some time ago, chances are your Rust version is out of date. Get the latest version of Rust by running ```rustup update```.

Go back to [Contents](#contents).

## Cargo. The Rust build tool and package manager

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