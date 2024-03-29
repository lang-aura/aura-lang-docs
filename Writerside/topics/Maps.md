# Map Type

## Initialization

Maps in Aura are a collection data type that associate keys with value expressions. They can be instantiated like this:
```
m := map[string : int]{
    "Hello": 1,
    "World": 2,
}
```
The `map` keyword is followed by the key and value types in brackets, separated by a colon. Maps can optionally be instantiated
with a collection of key-value pairs - in that case, the key-value pairs are specified in the curly braces that follow the
map's key and value types. Each key-value pair must follow the format: `<key>: <value>,`. The key and value expressions
are separated by a colon, and the value expression must be followed by a comma, even the final pair in the list.

Its also no problem to initialize an empty map. The curly braces are always required when creating a new map, so initializing
an empty map would look like this:
```
m := map[string : int]{}
```

## Type Specification

When specifying a map type, such as a function parameter's type, the syntax looks like this:
```
// Type specification
map[string : int]

// Function parameter example
fn f(m: map[string : int]) { ... }
```

## Indexing

Maps can be indexed to retrieve individual values. The index values must match the map's key type, and the return type of
the index operation will match the map's value type. For instance, a map whose signature is `map[string : int]` will be
indexed with strings and will return an integer. This would look like:
```
m := map[string : int]{
    "Hello": 1,
    "World": 2,
}

m["Hello"] // 1
```

## Methods

The Aura standard library includes a `maps` module containing methods that can be called directly on map objects. As an example,
to see how many key-value pairs are present in a map, you would call the `count` method:
```
m := map[string : int]{
    "Hello": 1,
    "World": 2,
}

m.count() // 2
```

These methods can also be called on map literals, like this:
```
map[string : int]{
    "Hello": 1,
    "World": 2,
}.count() // 2
```

To see a complete list of methods, see the standard library's [`maps` module](Standard-Library.md#maps "The `maps` module")