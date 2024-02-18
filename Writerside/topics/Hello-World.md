# Hello World

A typical "Hello world" program in Aura looks like this:

```
mod main

import aura/io

fn main() {
    io.println("Hello world")
}
```

All Aura programs must begin with a `mod` statement that defines the source file's containing module. Following
the `mod` statement is an `import` statement, which is used to include external modules in the current source file.
In this case, the built-in `aura/io` package is imported, which contains methods for performing input and output
operations. All Aura projects must define a `main` method, which is the project's entrypoint. In this program, the
`main` function calls the `println` function, which is defined in the `auro/io` package that was imported earlier in
the program.

Running this program with the Aura CLI tool via `aura run` will produce the output `Hello world`.

Congratulations! You've just written and run your first Aura program. The rest of this language tour will delve into
the details of Aura in more depth.