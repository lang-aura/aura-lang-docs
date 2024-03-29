# lists

`contains(l: [any], item: any) -> bool`

Checks if the supplied `item` is contained in `l`

`is_empty(l: [any]) -> bool`

Checks if the supplied list is empty

`length(l: [any]) -> int`

Returns an integer representing the number of items in the supplied list

`map_(l: [any], f: fn(any) -> any) -> [any]`

Applies `f` to each item in the supplied list, and returns a new list containing the output of each function call

`filter(l: [any], f: fn(any) -> bool) -> [any]`

Applies `f` to each item in the supplied list, and returns a new list containing all items in the supplied list that
evaluated to true

`reduce(l: [any], f: fn(any, any) -> any, start: any) -> any`

Reduces the supplied list to a single value by successively applying `f` to each item in the supplied list

`main(l: [int]) -> int`

Returns the minimum value in the supplied list of integers

`max(l: [int]) -> int`

Returns the maximum value in the supplied list of integers

`push(l: [any], item: any)`

Adds `item` to the end of the supplied list

`pop(l: [any]) -> any`

Removes the final value in the supplied list and returns it

`sum(l: [int]) -> int`

Returns the sum of all items in the supplied list of integers