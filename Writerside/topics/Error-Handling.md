# Error Handling

## `error` Type

Error handling in Aura is modelled off Go's approach, and the `error` type in Aura is considered a common type that can
be used anywhere a type is expected. This is opposed to other languages, such as Java and C#, that handle errors with
exceptions that interrupt a program's normal execution flow. A common error handling strategy in Aura might look like this:
```
fn f() -> error { ... }
```

Here, the function `f` returns an error to indicate success or failure of the function's execution. The `error` type is
nil-able, meaning it can be represented by the value `nil`. Therefore, to indicate successful execution, the function `f`
above can return `nil` instead of an `error` value to indicate success. If an error value is required, it can be constructed
with the function `err(message: string)`, which is found in Aura's prelude, meaning the programmer doesn't need to import it into
the source file before using (i.e. it can be called as if it had been defined in the same module: `err("Helpful error message")`)

Because Aura supports returning multiple values from a function, the `error` type can be coupled with another type. Whereas
a single `error` return type is only capable of encapsulating whether an error occurred, coupling an `error` type
with another type can provide a success value. An example:
```
fn f() -> (string, error) { ... }
// Typical error handling
s, e := f()
if err != nil { ... } // Handle error
```

When returning multiple types from a function, they must be enclosed in a set of parentheses and separated by a comma. In
this situation, the programmer will typically first check if the returned `error` type is nil. If not, an error has occurred
that should be handled. However, if the `error` is nil, the program continues, and `s` contains the success value that can
now be used elsewhere in the program.

## `check` Keyword

The `check` keyword is intended to make error handling a little bit easier in Aura. It can be used in certain situations
to replace the sometimes-tedious `if err != nil` check. Usage of the `check` keyword looks like this:
```
fn f() -> err { ... }

fn returns_err() -> error {
    check f()
}
```

The `check` keyword is placed before a function call that returns a single `error` type and nothing else. If the function 
call returns an error, and the enclosing function also returns an error, the `check` keyword will automatically return the
error.