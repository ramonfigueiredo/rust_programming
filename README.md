Some programming examples in Rust
===========================

## Contents
1. [The Rust programming language](#the-rust-programming-language)
2. [Installing Rust](#installing-rust)
3. [Cargo-The Rust build tool and package manager](#cargo-the-rust-build-tool-and-package-manager)
4. [Generating a new Rust project](#generating-a-new-rust-project)
5. [Adding Rust dependencies](#adding-rust-dependencies)
6. [Macro and println](#macro-and-println)
7. [Comments in Rust](#comments-in-rust)
8. [Data Types](#data-types)
9. [Variables](#variables)
10. [Constant](#constant)
11. [String](#string)
11. [Operators](#operators)
12. [Decision Making](#decision-making)
13. [Loop](#loop)
14. [Functions](#functions)
15. [Tuple](#tuple)
16. [Array](#array)
17. [Ownership](#ownership)
18. [Borrowing](#borrowing)
19. [Slices](#slices)
20. [Structure](#structure)
21. [Enums](#enums)
22. [Modules](#modules)
23. [Collections](#collections)
24. [Error Handling](#error-handling)
25. [Generic Types](#generic-types)
26. [Input Output](#input-output)
27. [File Input/ Output](#file-Input-and-output)
28. [Package Manager](#package-manager)
29. [Iterator and Closure](#iterator-and-closure)
30. [Smart Pointers](#smart-pointers)
31. [Concurrency](#concurrency)
32. [Rust Web Frameworks](#rust-web-frameworks)
33. [Other Rust Frameworks](#other-rust-frameworks)

## The Rust programming language

The [Rust programming language](https://www.rust-lang.org/) is a multi-paradigm, high-level, general-purpose programming language. Rust is popular for systems programming but also offers high-level features including some functional programming constructs. Rust runs really fast like C and C++, prevents almost all crashes, and eliminates data races. Rust is intended to be a language for highly concurrent and highly secure systems.

Graydon Hoare (a software developer) created Rust as a personal project while working at Mozilla Research in 2006. Mozilla officially sponsored the project in 2009. Since the first stable release in May 2015, Rust has been adopted by companies including Amazon, Discord, Dropbox, Facebook (Meta), Google (Alphabet), and Microsoft. In 2022, Rust became the third programming language used in the Linux kernel, after C and Assembly language.

* [Rust website](https://www.rust-lang.org/)
* [Getting started with Rust](https://www.rust-lang.org/learn/get-started): Quickly set up a Rust development environment and write a small app.
* [Rust playground](https://play.rust-lang.org/): A browser interface to the Rust compiler to experiment with the language.
* [The Rust programming language's official book](https://doc.rust-lang.org/book/): The Rust Programming Language will give you an overview of the language from first principles. You’ll build a few projects along the way, and by the end, you’ll have a solid grasp of the language.
* [Rust by examples](https://doc.rust-lang.org/stable/rust-by-example/): Rust by Examples (RBE) shows off a bunch of code, and keeps the text to a minimum. It also includes exercises!
* [Rustlings course](https://github.com/rust-lang/rustlings/): Rustlings guides you through downloading and setting up the Rust toolchain, and teaches you the basics of reading and writing Rust syntax, on the command line. It's an alternative to Rust by Example that works with your own environment.
* [crates.io](https://crates.io/): The package registry for Rust.

**Note:** Rustaceans are people who use Rust, contribute to Rust, or are interested in the development of Rust.

### Application programming languages versus Systems programming languages

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

## Macro and println

Using the ```println!``` macro syntax:

```
println!(); // prints just a newline
println!("hello "); //prints hello
println!("format {} arguments", "some"); //prints format some arguments
```

Rust provides a powerful macro system that allows meta-programming. 
As you have seen in the previous example, macros look like functions, except that their name ends with a bang(!), but instead of generating a function call, macros are expanded into source code that gets compiled with the rest of the program. Therefore, they provide more runtime features to a program unlike functions. Macros are an extended version of functions.

Go back to [Contents](#contents).

## Comments in Rust

Single-line comments ( // ) − Any text between a // and the end of a line is treated as a comment

Multi-line comments (/* */) − These comments may span multiple lines.

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

## Rust Web Frameworks

The two most popular options for web development frameworks in Rust are Actix Web and Rocket. Both of them provide type safety in their requests and lightning-fast performance.

Go back to [Contents](#contents).

### Most popular Rust web frameworks:
- [Rocket](https://rocket.rs/)
  - Rocket is a web framework written in Rust. Its design was inspired by Rails, Flask, Bottle, and Yesod.
  - Rocket is a web framework for Rust that makes it simple to write fast, secure web applications without sacrificing flexibility, usability, or type safety.
  - Rocket is known for being very approachable and universal. 
  - It is very adaptable and prioritizes speed; you won't need to spend a lot of time setting up a project before you can begin coding.
  - Rocket claims to be "boilerplate free," which means that all of the code generated by Rocket is generated automatically and you won't waste time writing it. 
  - Rocket is entirely type-safe, eliminating the chance of potential server issues.
  - Rocket makes sure that all of the types in a particular handler can be generated from the incoming request whenever you submit a new request.
  - Rocket is an async web framework for Rust with an emphasis on security, performance, flexibility, and usability.
  - Features:
    - Async streams
    - Boilerplate free
    - Easy to use
    - Extensible
    - Testing library
    - Type safe

- [Actix Web](https://actix.rs/)
  - Actix Web is a powerful, pragmatic, and extremely fast web framework for Rust.
  - Features:
      - Client/server WebSockets support 
      - Full Tokio compatibility
      - Keep alive and slow requests handling
      - Middlewares
      - Multipart streams
      - SSL support using OpenSSL or Rustls
      - Static assets
      - Streaming and pipelining
      - Supports HTTP/1.x and HTTP/2

Go back to [Contents](#contents).

### Other Rust web frameworks:
- [Warp](https://github.com/seanmonstar/warp)
  - A super-easy, composable, web server framework for warp speeds.
  - The fundamental building block of warp is the Filter: they can be combined and composed to express rich requirements on requests.
- [Tide](https://docs.rs/tide/0.16.0/tide/)
  - Tide is a minimal and pragmatic Rust web application framework built for rapid development. It comes with a robust set of features that make building async web applications and APIs easier and more fun.
- [Gotham](https://github.com/gotham-rs/gotham)
  - A flexible web framework that promotes stability, safety, security and speed.

Go back to [Contents](#contents).

## Other Rust Frameworks

- [Tauri](https://tauri.app/)
  - Tauri is a popular framework for creating incredibly small, lightning-quick binaries for all popular desktop operating systems. 
  - For the creation of their user interface, developers can incorporate any frontend framework that compiles to HTML, JavaScript, and CSS. 
  - The application's backend is a rust-sourced binary with an API that the frontend can use to communicate.
  - Features:
    - App storage
    - App tray
    - Core plugin system
    - Desktop bundler
    - GitHub action
    - Native notifications
    - Scoped filesystem
    - Self-updater
    - Sidecar

Go back to [Contents](#contents).

- [Yew (Rust / Wasm client web app framework)](https://github.com/yewstack/yew)
  - Yew is a cutting-edge Rust framework for building WebAssembly multi-threaded frontend web applications. 
  - It includes a macro for defining interactive HTML using Rust expressions. 
  - Yew should be incredibly familiar to developers who have used JSX in React. 
  - Features:
    - Component-based framework 
    - Portable low-level language
    - Supported in all major modern browsers 
    - Uses own virtual-DOM representation

Go back to [Contents](#contents).

- [Juniper](https://github.com/graphql-rust/juniper)
  - Juniper is used to create type-safe, lightning-fast GraphQL servers
  - Instead of including a web server, Juniper offers building elements that make integrating with pre-existing servers simple. 
  - For the Actix, Hyper, Iron, Rocket, and Warp frameworks, it offers an optional pre-built integration that includes inbuilt Graphiql and GraphQL Playground for simple debugging.
  - Features:
    - Agnostic to serialization format and network transport
    - Both synchronous and asynchronous execution are supported
    - Follows a code-first approach
    - Supports the full GraphQL query language

Go back to [Contents](#contents).

- [Dioxus](https://github.com/DioxusLabs/dioxus)
  - Dioxus is a virtual DOM-based UI framework with a React-like design that supports creating cross-platform apps for web, mobile, and desktop. 
  - It supports concurrency and async, props, an integrated error handler, state management, and more. 
  - It also supports component-based architecture.
  - Dioxus is a lightweight, quick, and practical Rust framework for creating cross-platform user interfaces. 
  - Webapps, desktop apps, static sites, mobile apps, TUI apps, liveview apps, and other types of apps can all be delivered using Dioxus. 
  - Dioxus can be used as a platform for any renderer because it is completely renderer agnostic.
  - Features:
    - Comprehensive inline documentation
    - Extremely memory efficient
    - Incredibly ergonomic and powerful state management
    - Multi-channel asynchronous scheduler

Go back to [Contents](#contents).

- [Stdweb](https://github.com/koute/stdweb)
  - A standard library for the client-side Web
  - Enables Rust to interact directly with JavaScript web APIs. 
  - It was designed to enable developers to produce fully functional JavaScript apps in Rust by facilitating simple API binding between the two languages to enhance speed and performance.
  - Closures, arbitrary structure, and common web API elements like DOM, events, and windows are supported by stdweb.
  - Features:
    - Allow a high degree of interoperability
    - Closures are also supported
    - Provide Rust bindings to the Web APIs
    - Support experimental Parcel plugin

Go back to [Contents](#contents).

- [Percy](https://github.com/chinedufn/percy)
  - Percy is a collection of Rust libraries used to create frontend web applications that are driven by WebMeeting. 
  - Percy assists in triggering server-side rendering. 
  - The task excels in creating single-page purposes (SPAs) that are friendly to search engines. 
  - For the creation of digital DOMs, Percy provides an html! macro. 
    - These can be used for operations in the utility's backend or rendered as DOM components for the frontend. 
  - You can build apps using Percy that support either server-side rendering only, client-side rendering only, or both server and client-side rendering.
  - Features:
    - Allows building search engine-friendly browser applications 
    - CSS in Rust 
    - Supports server-side rendering


Go back to [Contents](#contents).

- [Sycamore](https://github.com/sycamore-rs/sycamore)
  - A reactive framework that is similar to SolidJS in speed, ease, and use is named Sycamore. 
  - It can be used to build Rust net purposes that make use of WebMeeting's abilities. 
  - You won't need to write JavaScript because Sycamore includes many of the Rust functions you'll need to build an online app frontend. 
  - In addition, Sycamore provides Wasm-Bindgen and a router via web-sys or js-sys compatibility for JavaScript. 
  - The goal of the task is to fast launch testing and CSS performance.
  - Features:
    - Ergonomic and intuitive 
    - Excellent documentation 
    - Lightning speed 
    - No JavaScript

Go back to [Contents](#contents).

- [Gloo](https://github.com/rustwasm/gloo)
  - Gloo is a modular toolkit. 
  - It is a group of libraries that offer convenient Rust wrappers for browser APIs. 
  - Since using web-sys/js-sys directly is very challenging and inconvenient, gloo offers wrappers around the raw bindings to make it simpler to use those APIs. 
  - Because of this, it is referred to as a "toolkit" rather than a "library" or "framework." 
  - Gloo ought to be a flexible grouping of utility crates that can be used separately or collectively. 
  - Features:
    - Cultivate the Rust and Wasm library ecosystem
    - Fast
    - Idiomatic
    - Modular toolkit
    - Reliable
    - Small
    - Support both small, targeted libraries and Web applications

Go back to [Contents](#contents).

- [Seed](https://github.com/seed-rs/seed)
  - With an Elm-like architecture, Seed is a Rust frontend framework for building quick and dependable web applications. 
  - Including the templating system, it is entirely written in Rust. 
  - Elm architecture serves as the foundation for internal state management. 
  - Seed provides a batteries-included approach with a focus on developer experience. 
  - This saves time on installing dependencies and writing boilerplate.  
  - As a result, Rust will be used for all formatting, commenting, and linting. A JavaScript XML (JSX)-like syntax, on the other hand, depends on IDE extensions to enhance the developer experience. 
  - With Seed, you can create the frontend with all of Rust's advantages, including speed, safety, and way too many other things to list. For both experienced users and newcomers to Rust, it offers comprehensive and clear documentation.

Go back to [Contents](#contents).
