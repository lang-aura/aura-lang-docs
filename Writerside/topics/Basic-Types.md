# Basic Types

## `int` and `float`

Aura supports just the one `int` type (as opposed to `int32`, `int64`, etc. in Go) and just one `float` type (unlike `float32`
and `float64` in Go).

To aid in readability, Aura supports inserting underscores in number literals. Although these are designed with the idea that
they will be used in long number literals and at natural separator places to distinguish between the thousands, millions, etc.
digits, these underscores can be used anywhere in any number literal.

```
// All of these examples are valid Aura syntax
1_000 // 1,000

10_00 // Also 1,000 (looks a little weird, but the underscores can be used at the programmer's discretion)

1_000.000_01 // The underscore can also be used in floats after the decimal point

1_000_000_000 // The programmer may use as many underscores in a single number literal as they please
```

## `string`

String literals are denoted in Aura by enclosing a string of text in double quotes. Single quotes are reserved for the
[`char`](Basic-Types.md#char) data type.

```
"Hello world"
```

## `char`

Char literals are denoted in Aura by enclosing a single character in single quotes. Although a single character enclosed
in double quotes is valid Aura, that would create a new [`string`](Basic-Types.md#string) data type, not a char.

```
'a'
```

## `bool`

Aura supports the boolean values `true` and `false`

## `nil`

Aura supports the `nil` data type, which indicates the absence of a value. Data types that do not define a default value
are implicitly understood to have a default value of `nil`. Therefore, initializing a new variable with a non-defaultable
type without an initial value will implicitly assign the value of `nil` to the new variable.

```
// Since the char type does not define a default value and no initial value was provided,
// the `c` variable has a value of nil
let c: char
```

## `any`

The parent type of all other types. When a parameter is defined with a type of `any`, any type can be passed in as an
argument.

```
fn f(a: any) { ... }

// All valid
f(5)
f("Hello world")
f([int]{ 1, 2, 3 })
```