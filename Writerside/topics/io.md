# io

The `io` module provides functions for dealing with input/output.

`printf(format: string, a: ...any)`

Constructs an output string by inserting each value in `a` into the `format` string and then printing the resulting string
to the standard output. For example:
```
import aura/io

io.printf("%d\n", 5) // 5\n

name := "Bob"
io.printf("Hello, %s", name) // Hello, Bob
```

Aura's supported format specifiers are the same as [Go's format specifiers](https://pkg.go.dev/fmt#hdr-Printing).

`println(s: string)`

Prints the supplied string to the standard output. A newline character is appended to the string before printing.

```
import aura/io

io.println("Hello world") // Hello world\n
```

`print(s: string)`

Prints the supplied string to the standard output.

`eprintln(s: string)`

Prints the supplied string to the standard error. A newline character is appended to the string before printing.

`eprint(s: string)`

Prints the supplied string to the standard error.

`readln() -> string`

Reads a single line from the standard input. The trailing newline is removed before the line is returned.

`read_file(path: string) -> string`

Reads the entire content of the file located at the supplied `path`, and returns the contents as a string

`read_lines(path: string} -> [string]`

Reads the entire content of the file located at the supplied `path`, and returns the contents as a list of strings where
each item in the returned list corresponds to one line in the file.

`write_file(path: string, contents: string)`

Writes the supplied `contents` to the file located at the supplied `path`. If the file already exists, it is truncated
before the write occurs.