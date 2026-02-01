---
date: 2026-02-01
---

*Cargo* is the official [[Rust]] [[Package Manager]] and build system that orchestrates fetching dependencies, [[Compiler|compiling]] code, and distributing libraries.
* **`cargo new <name>`**: Creates a new Rust project directory containing a `Cargo.toml` manifest and a boilerplate "Hello, World!" source file
* **`cargo build`**: Compiles the project and its dependencies, placing the resulting artifacts in the `target/` folder
* **`cargo run`**: A convenience command that compiles the code (if necessary) and immediately executes the binary in one step