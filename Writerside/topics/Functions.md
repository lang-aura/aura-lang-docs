# Functions

## Declaration

Functions are declared using the `fn` keyword, and are optionally preceded with the `pub` keyword to make it public.
```
// Without the `pub` keyword, this function is declared as a private function, meaning that is cannot be used outside of
// the module where it was declared
fn f() { ... }

// Here, the `pub` keyword means that this function can be called outside its defining module
pub fn f_pub() { ... }
```

## Parameters

Parameters are defined in the form `name: type`, and multiple arguments are separated by commas.
```
// This function declares two parameters, an integer and a string
fn f(i: int, s: string) { ... }
```
When calling a function, values must be passed in that correspond to each parameter.
```
f(5, "Hello world")
```
In this case, each argument passed in must match the type of the corresponding parameter. In order to pass in the arguments
out of order, or just to be more clear about the name of each argument, you can precede each argument with the name of the
parameter and a colon.
```
f(i: 5, s: "Hello world")
```
All arguments in a function call must either be positional or named -- they cannot be mixed.

## Variadic Parameters

Parameters can be declared as variadic like so:
```
fn f(i: int, strs: ...string) { ... }

// This means that multiple strings may be passed into the second parameter of this function
// All of these function calls are legitimate
f(5, "Hello world")
f(5, "Hello", "world")
f(5, "How", "are", "you", "?")
```
Functions may only have one variadic parameter, and it must be the last parameter in the parameter list. Attempting to define
a variadic parameter in a position other than the last one will result in an error.

## Default Values

Parameters may be defined with default values, which must be a literal value.
```
fn f(i: int, s: string = "Hello world") { ... }
```
In this case, passing in a value for the `s` parameter is optional. If no value is provided when calling the function, the
pre-defined default value will be used. Default values do not need to be the last parameter in the parameter list, however
using the default value of a parameter that is not last in the list requires the use of named arguments.
```
fn f(i: int, s: string = "Hello world") { ... }
// Here, we aren't passing in a value for the `s` parameter, meaning we'll be accepting its default value
f(5)

fn f2(i: int = 5, s: string) { ... }
// Here, if we want to use the default value of the `i` parameter, we need to use named parameters
f2(s: "Hello world")
```

## Return Values

Return values are defined with an arrow and the return value's type after the parameter list.
```
// This function returns a string type
fn f(i: int) -> string { ... }
```