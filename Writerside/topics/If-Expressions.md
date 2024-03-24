# If Expressions

`if` expressions in Aura are declared with the following syntax:
```
if true {
    ...
}
```

## `yield` Keyword

It's also important to note that `if` expressions are capable of returning a value, which is done with the `yield` keyword.
So, returning a value looks like this:
```
s := if true {
    yield "Hello"
} else {
    yield "World"
}
```

When returning a value, the return value of both branches must be the same.

## `return` Keyword

The programmer may still use the `return` keyword inside an `if` expression, but it returns the supplied value from the
nearest enclosing function scope. This means that, in an example like this:
```
s := if true {
    return "Hello"
} else {
    yield "World"
}
```
the `"Hello"` value will bypass the `s` variable completely and be returned from the enclosing function. However, if the
value of the `if` expression's condition evaluates to false (which, of course, is impossible when the condition is `true`)
the value of `s` will become `World`.

## Required `else` Branch

When the return value of an `if` expression isn't used, the `if` expression is not required to have an `else` branch. So,
this would be fine:
```
if false {
    return "Hello world"
}
```

However, if the return value is being stored in a variable, the `else` branch is required.
```
s := if true {
    yield "Hello"
} else { // This branch is required because we're storing the yielded value in `s`
    yield "World"
}
```