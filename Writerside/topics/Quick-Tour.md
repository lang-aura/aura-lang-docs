# Quick Tour

This page presents a brief tour of basic Aura syntax and concepts. Where appropriate, sections will include a link to a page containing
more detailed information.

## Module Definition and Imports

All Aura source files must begin with a `mod` declaration, and any imports should come immediately after.

```
mod main

import aura/io
```

See [Modules](Modules.md "Detailed information on defining modules in Aura") and [Imports](Imports.md "Detailed information on importing external modules")

## Program Entrypoint

Every Aura project must define exactly one `main` function, which is the project's entrypoint.

```
fn main() {
    ...
}
```

See [Project Structure](Project-Structure.md "Detailed information on an Aura project's structure")

## Printing to stdout

Printing to the standard output is done with functions exported by the `io` standard library module

```
import aura/io

// Prints to stdout; does not append a newline
io.print("Hello world")

// Prints to stdout; appends a newline
io.println("Hello world")

// Assembles string and prints to stdout
io.printf("%s %d\n", "Hello world", 5)
```

See [Standard Library](Standard-Library.md "The Aura standard library") and [`io` module](Standard-Library.md#io "Provides functions to dealing with input/output")

## Functions

Functions are defined with the `fn` keyword. A typical declaration would look like:

```
fn f(i:int) -> string {
    ...
}
```

See [Functions](Functions.md "Detailed information on defining functions in Aura")

## Variables

Variables can be defined with the `let` keyword like so:

```
let i: int = 5
```

They can also be defined with shorter syntax that omits the `let` keyword:

```
j := 5
```

Variables are defined as immutable by default. To define a variable as mutable, use the `mut` keyword:

```
let mut i: int = 5
mut j := 5
```

See [Variables](Variables.md "Detailed information on defining variables in Aura")

## Classes and Structs

Classes are defined with the `class` keyword, and can contain zero or more parameters and zero or more methods.

```
class Greeter(name: string) {
    pub fn say_hi() { ... }
}
```

And structs are defined with the `struct` keyword:

```
struct ApiResponse(id: string, first_name: string, last_name: string)
```

To create instances of classes and structs, their names are used in a function call:

```
greeter := Greeter("Bob")
resp := ApiResponse("1", "John", "Doe")
```

See [Classes](Classes.md "The Aura `class` specification") and [Structs](Structs.md "The Aura `struct` specification")

## Comments

Single line comments:

```
// Single line comment
// Goes to the end of the current line
```

Multi-line comments:

```
/* Multi-line comment
that can span multiple lines
and goes until the closing
token here -> */
```

See [Comments](Comments.md "Detailed information on defining comments in Aura")

## Conditional Expressions

`if` expressions in Aura are expressions capable of returning a value, which is done with the `yield` keyword.

```
i := if true {
    yield 1
} else {
    yield 0
}
```

See [`if` expressions](If-Expressions.md "The Aura `if` expression specification")

## Loops

`for` loops:

```
for i := 0; i < 10; i++ {
    ...
}
```

`foreach` loops:

```
foreach item in items {
    ...
}
```

`while` loops:

```
while true {
    ...
}
```

See [Loops](Loops.md "Detailed information on defining loops in Aura")

## Collections

Aura supports two collection types.

```
// Lists
l := [string]{ "Hello", "world" }

// Maps
m := map[string : int]{
    "Hello": 1,
    "World": 2,
}
```

See [Types](Type-System.md "The Aura type system"), [Lists](Lists.md "The Aura list type"), and [Maps](Maps.md "The Aura map type")