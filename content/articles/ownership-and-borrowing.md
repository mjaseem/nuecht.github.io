---
draft: true
title: "Ownership and Borrowing"
date: 2024-01-20
topics: [rust]
weight: 10
maturity: seedling
---

Rust's memory model eliminates entire classes of bugs at compile time. The key insight is that every value has exactly one owner, and when the owner goes out of scope, the value is dropped — no garbage collector needed, no manual `free`.{{< sidenote ref="2024-01-15-hello-world" >}}

This isn't magic. The compiler tracks ownership statically and inserts the necessary cleanup code. The cost is zero at runtime; you pay only at compile time, in the form of constraints you have to reason about.

## Borrowing

You can temporarily lend a value without transferring ownership. The borrow checker enforces two rules simultaneously:

- You may have any number of immutable references, **or**
- Exactly one mutable reference — never both at once

This eliminates data races by construction. Two threads cannot hold a mutable reference to the same data simultaneously; the type system makes it impossible to express.{{< sidenote ref="2024-02-10-on-research" >}}

## Lifetimes

Every reference has a lifetime — the scope for which it is valid. Most of the time, the compiler infers lifetimes and you never write them. When it cannot infer, you annotate explicitly.

The lifetime system ensures that references never outlive the data they point to. Dangling pointers are a compile error.
