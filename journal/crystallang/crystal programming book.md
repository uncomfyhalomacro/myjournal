---
tags:
  - crystal
  - ruby
  - llvm
  - repl
  - book
---

---

# Crystal Notes
## Crystal Programming Book

Exploring the Crystal Programming Language

---

## Brief History

- Crystal was created in 2011
- Manas Technology Solutions created the language (https://manas.tech)
- Authors
  - Ary Borenszweig
  - Brian Cardiff
  - Juan Wajnerman
- Has over 500 Contributors and growing
- Production Ready
- Source code is found at https://github.com/crystal-lang/crystal

---

## Features

- Static Typing
- Ruby-esque syntax
- Compiles into machine code
- Leverages LLVM
- Expressive as Ruby
- Concurrency
- Low-level; can call C libraries or assembly
- Project Manager called Shards

The book was written when Crystal was at version 1.2.2, this note was written
at version 1.7.3.

---

Although the language is much inspired by Ruby, it's definitely a new language.

---

## Fast

Crystal is fast using **ahead-of-time compilation**. 

Crystal's compiler is **built upon LLVM**.

---

# Crystal's Code and Syntax

---

## Sample code

```crystal
def get_name
  print "What's your name? "
  read_line
end

puts "Hello, " + get_name + "!"
```

---

## Sample code (continued)

Running crystal is as easy by invoking either `run` to run it directly, or `build` to build it as a binary.

```
$ crystal run hello_name.cr
What's your name? Soc
Hello, Soc!

$ crystal build hello_name.cr

$ ./hello_name
What's your name? Soc
Hello, Soc!
```

---

# Values and expressions

---

## Primitive data types

- Integers
- Booleans
- Floats

---

## Variable assignment

```crystal
score = 38
distance = 104
score = 41

p score

# Multi assignments
emma, josh = 16, 19
p josh
p emma

# Swap the values
josh, emma = emma, josh
p josh
p emma
```

---

## Variable assignments (continued)

```crystal
# Constants are declared with uppercase letters
# They usually are in all caps.
LARGE_CONSTANT = 1000
PI = 3.14

# Constants can't be reassigned
# This line of code below will errors
# with "Error: can't reassign to constant"
LARGE_CONSTANT += 1
```




