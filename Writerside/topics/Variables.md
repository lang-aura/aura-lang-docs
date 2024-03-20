# Variables

## Declaration
Variables can be declared in two different ways. First, there is the `let`-style declaration that looks like this:
```
let i: int = 5
```
When declaring a new variable in this way, the type annotation is required. To omit the type annotation, you can use the shorter declaration syntax, which looks like this:
```
i := 5
```
In this case, the type of the variable will be inferred from the type of the initializer expression.
## Mutability
By default, variables are declared as immutable, meaning their values cannot be changed after their initial declaration. However, variables can be declared as mutable via the `mut` keyword, which must precede the variable's name, no matter which declaration option is used. For example, a variable can be declared as mutable like so:
#### Long syntax
```
let mut i: int = 5
```
#### Short syntax
```
mut i := 5
```
## Initializers
Variables are not required to be declared with an initializer, in which case they are initially assigned their type's default value. When omitting a initializer, the variable must be declared with the longer `let`-style syntax. As an example, this variable declaration:
```
let i: int
```
will result in a variable `i` whose initial value is `0`. Other common default values include `0.0` for floating point numbers and `""` for strings. The default value of compound types is composed of the default value for each of the compound type's attributes.