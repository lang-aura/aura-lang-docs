# Comments

Comments in Aura can be defined in two different ways. First, single-line comments are preceded with `//`:

```
// This is a single-line comment, and will continue to the end of this line
// The programmer may define multiple single-line comments in a row, but each one must begin with `//`

i := 5 // Single-line comments don't need to be defined at the very beginning of a line, but they will always extend to the end of the line
```

These are great for short comments, or even a small number of single-line comments defined in a row. However,
for longer comments, the programmer may instead wish to define a multi-line comment between `/*` and `*/`:

```
/* Here is a multi-line comment. Unlike single-line comments, which extend to the end of the current line,
multi-line comments will extend to their closing token, no matter how many lines it spans. These comments
are useful when providing more detailed information that won't fit onto a single line, such as a documentation
comment above a function declaration */
fn f(i: int) -> int {
    ...
}
```