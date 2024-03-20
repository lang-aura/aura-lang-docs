# Type System

## Default Values
Some types provide a default value that can be used in a variable declaration when no initializer is provided. These types are:
* `string`: an empty string
* `int`: `0`
* `float`: `0.0`
* `list`: an empty list
* `map`: an empty map

So, for example, a variable declared like so:
```
let i: int
```
will have a value of `0`, and this variable declaration:
```
let m: map[string : int]
```
will result in the variable `m` being assigned to an empty map whose keys are strings and values are integers.