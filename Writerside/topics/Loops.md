# Loops

## For Loops
The first type is a C-style `for` loop.

```
for i := 0; i < 10; i++ {
    ...
}
```
The main difference is that Aura does not require parentheses around the loop's conditions. Additionally, the variable initialization can use the short syntax. However, the variable initialization could use the longer syntax.
```
// Also valid syntax, although more verbose and less common
for let i: int = 0; i < 10; i++ {
    ...
}
```

## Foreach Loops
The second type of loop is a `foreach` loop.

```
// A foreach loop can iterate over Aura collections,
// such as this list of strings
items := [string]{
    "Hello",
    "world"
} 
```
{collapsible="true" collapsed-title="items declaration"}
```
foreach item in items {
    ...
}
```
Unlike `for` loops, `foreach` loops are not capable of providing an index parameter, meaning that the programmer is not able to determine the index of each individual iteration.

## While Loops
`while` loops iterate until their condition evaluates to false.
```
i := 0
while i < 10 {
    ...
    i++
}
```
Here, the `while` loop will complete ten iterations, at which point the value of `i` will be 11 and the loop's condition will be false, ending its execution.