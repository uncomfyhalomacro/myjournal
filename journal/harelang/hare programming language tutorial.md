# hare programming language tutorial

---
tags:
  - language hopping
  - harelang
  - systems language
  - low-level language
---

## Hare's components

- HareC, the bootstrap compiler
- Hare
  - Stdlib
  - Builder

## Tutorials

### Introduction

#### Hello World

- `main` is the _entry point_ of programs in hare. Similar to Rust.
- `use` to import modules such as `fmt`
- `!` is an error assertion operator. Discouraged to use.

code sample in the tutorial

```hare
use fmt;

export fn main() void = {
  fmt::println("Hello World!")!;
};
```

- Removing `!` causes an error since the _programmer is desired to handle this_ as
described in [Error handling](####error-handling).

#### Hare basics

##### Functions and parameters

- `functions` may accept a list of parameters by placing them
inside `()` tokens when declaring a function.
  - `greet` function here accepts `user` of type `str`.

Use `haredoc` to check **documentation** such as `io::error`. Very useful for learning
available `stdlib`.

##### Variables and COnstants

- `let` to define a non-constant variable.
- `const` to define a variable as a constant.

Constants, like most programming languages, _can't be modified_. However, you can
_re-bind_ it by creating a variable with the same name like so:

```hare
	const source = os::open("main.ha")!;
	const source = io::drain(source)!;
	const source = strings::fromutf8(source)!;
	const source = strings::split(source, "\n");
```

As seen from above, you may also want to change its type.

##### Hare's types

Numeric Types:

- `int` ⇒ signed integer
- `uint` ⇒ unsigned integer
- `u8` ⇒ unsigned 8-bit integer
- `f32` ⇒ 32-bit floating point number

Numeric types can be _inferred_ from a suffix from the first letter of the type
along with the number of bits e.g. `i`, `u8`.

Declaring a variable with an signed integer of `10` can be done with `a = 10i`.

Other types:

- `str` is the string type.
- `struct` the struct type. Example:

```hare
c: struct { x:int, y:int };
```

Array types are invoked by putting a type after the bracket e.g. `[]str`, `[]u8`.

Declaring an array as a variable should have a definite length.

```hare
a; [4]int = [1, 2, 3, 4]
```

#TODO: add slices

#### Error handling



