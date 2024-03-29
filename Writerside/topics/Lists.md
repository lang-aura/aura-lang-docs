# List Type

Lists in Aura are a collection type that contains items of the same type. They can be instantiated like this:
```
l := [int]{ 1, 2, 3 }
```

The type of the list's contents is written inside a pair of square brackets, followed by a set of curly braces. In this
case, the list is initialized with the values `1`, `2`, and `3`, but you can initialize an empty list, too:
```
l := [int]{} // A list containing zero elements to start
```

All items in a list must be the same type, and must match the type specified when creating the list

## Type Specification

A list's type is specified like this:
```
[int] // Type specification

// Function parameter example
fn f(l: [int]) { ... }
```

## Indexing

Lists can be indexed to retrieve individual or a range of values. Index values must be integers, and are 0-based (i.e. the
first item in the list is at index 0). Index values are added after the list and wrapped in square brackets, like this:
```
l := [string]{ "Hello", "world" }

// Fetch the first item in the list
l[0] // Hello

// Fetch the last item in the list
l[-1] // world
```

An indexing operation can also fetch a range of values from a list, which is done like this:
```
l := [int]{ 1, 2, 3, 4, 5 }

// Fetch the first two items in the list
l[0:2] // The lower bound is inclusive and the upper bound is exclusive

// Fetch the first two items in the list, part 2
l[:2] // Omitting the lower bound begins at the beginning of the list

// Fetch the last two items in the list
l[-2:] // Omitting the upper bound will fetch until the end of the list

// Fetch all items in the list
l[:] // Omitting both bounds will fetch all items
```

## Methods

The Aura standard library includes a `lists` module containing methods that can be called directly on list objects. As an example,
to see how many items are present in a list, you would call the `count` method:
```
l := [int]{ 1, 2, 3 }

l.count() // 3
```

These methods can also be called on list literals, like this:
```
[int]{ 1, 2, 3 }.count() // 3
```

To see a complete list of methods, see the standard library's [`lists` module](Standard-Library.md#lists "The `lists` module")