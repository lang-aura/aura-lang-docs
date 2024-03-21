# Imports

## Import Statements

There are two different types of modules that can be imported into an Aura source file. The first are standard library modules, which always begin with `aura`.

For example,
```
import aura/io
```
will import the standard library's `io` package.

The second type of module that can be imported is modules located on the local file system in the same Aura project. These modules are imported via their path within the project.

For example, consider the following project structure:

```
| src/
    |- main.aura
    |- common/
        |- common.aura
```
The import path of local imports begin after the `src` directory and goes to the imported file's directory. Therefore, `main.aura` can import `common.aura` with the following statement:
```
import common
```

## Import Aliases

When importing modules, they can be aliased using the `as` keyword. For example:

```
import aura/io as stdlib_io
import common as c
```

The `as` keyword can be used when importing both standard library and local modules. Once an imported module has an alias, the alias is used as the module's name for the entire source file. For example, once the `io` package has been aliased with `stdlib_io`, the programmer will call public functions in the `io` package like so:

```
stdlib_io.println("Hello world")
io.println("Hello world") // Invalid once the `io` package has been aliased
```

## Multiple Imports

When importing multiple modules, the programmer may streamline the import statements by collecting the imported modules together with one `import` keyword.

```
import (
    aura/io
    common
)
```

## Import Scopes

Imports are scoped to the entire Aura source file, and must be included at the top of the file before any other declarations.

```
mod main

// Imports should appear at the top of the file, after the `mod` statement
import aura/io

fn main() {
    // An `import` statement here is illegal
    import local_module
    
    s := f("Hello world")
    io.println(s)
}

// This import statement is also illegal. Although it is located in the file's top-level scope, it is placed after the
// declaration of the `main` function, which is not allowed
import another_local_module

fn f(s: string) -> string {
    ...
}
```