# strings

The `strings` module provides methods that operate on strings. These methods are not called like other methods in the
stdlib (i.e. `strings.to_upper()`). Instead, these methods are invoked as methods on the strings themselves. Therefore,
for each of the functions in this module, the first parameter is always a string, which won't be included in the method
call when invoking the function. As an example, the `to_lower` function has a function signature of `to_lower(s: string) -> string`,
but is invoked like `"Hello world".to_lower()` with an empty parameter list because the `s: string` parameter is represented
by the callee `"Hello world"` when invoking the method.

`to_lower(s: string) -> string`

Converts all characters in the supplied string to lowercase

`to_upper(s: string) -> string`

Converts all characters in the supplied string to uppercase

`contains(s: string, sub: string) -> bool`

Checks if `s` contains the supplied `sub` string

`length(s: string) -> int`

Returns the length of the supplied string

`split(s: string, sep: string) -> [string]`

Splits the supplied string, with `sep` used as the delimiter

`to_int(s: string) -> int`

Parses the supplied string as an integer