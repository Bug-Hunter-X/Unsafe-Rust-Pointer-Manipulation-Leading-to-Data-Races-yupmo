# Unsafe Rust Pointer Manipulation Leading to Data Races

This repository demonstrates a common issue in unsafe Rust: manipulating data through raw pointers without proper care, leading to potential data races, undefined behavior, and crashes. The `bug.rs` file contains the problematic code, while `bugSolution.rs` provides a safer alternative.

## Bug Description
Directly modifying a vector's contents via its raw pointer is unsafe. If multiple threads try to access or modify the data concurrently, or if the underlying memory is deallocated, it can result in data corruption or panics. This is not an uncommon problem in unsafe Rust codes and therefore requires thorough understanding of memory management practices.

## Solution
The recommended approach is to avoid unsafe code wherever possible. If necessary, the use of safe abstractions is recommended. The example in `bugSolution.rs` uses safe methods such as indexing to modify the vector's contents.