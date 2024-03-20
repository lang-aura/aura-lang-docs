# Interfaces

## Declaration
Interfaces in Aura can be declared using the `interface` keyword like so:
```
interface IGreeter { ... }
```
Interfaces can be declared as either public or private using the `pub` keyword preceding the `interface` keyword. The previous example defines a private interface - to declare a public one, you could update the interface declaration like so:
```
pub interface IGreeter { ... }
```
The body of an interface contains any methods that must be implemented by classes that implement the interface. These methods in the interface's body should not contain function bodies, and are implicitly understood to be public, meaning they do not need the `pub` visibility modifier. An example interface might look like this:
```
pub interface IGreeter {
    say_hi(name: string) -> string
}
```
## Implementation
Classes must explicitly implement an interface, which is done like so:
```
class Greeter : IGreeter { ... }
```
In this case, the `Greeter` class must implement the `say_hi` method defined in the `IGreeter` interface, and its implementation of the `say_hi` method must be marked with the `pub` visibility modifier. Failure to do so will result in an error during the compilation process.

Classes can implement any number of interfaces. When implementing more than one interface, the interfaces should be separated by a comma, like so:
```
class Greeter : IGreeter, ISmallTalker { ... }
```