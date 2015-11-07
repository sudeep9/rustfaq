# C++ types and their equivalent in Rust

### What are the equivalent types between C++ & rust w.r.t mutability rules?


In C++

```c++
int n = 10; // #1
const int n = 20; //#2
int *p = &n; //#3
const int *p = &n; // #4
int* const p = &n; // #5
const int* const p = &n // #6
```

In Rust

```rust
let mut n = 10 as i32; // #1
let m = 20 as i32; // #2

// EXACTLY EQUIVALENT
let mut ptr: *mut i32 = &mut n; // #3
let mut ptr: *const i32 = &n; // #4
let ptr: *mut i32 = &mut n; // #5
let ptr: *const i32 = &n; // #6

// ROUGHLY EQUIVALENT
let mut ptr = &mut n; // #3
let mut ptr = &n; // #4
let ptr = &mut n; // #5
let ptr = &n; // #6
```
