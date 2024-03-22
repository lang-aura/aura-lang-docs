# Classes

Classes in Aura are defined with the `class` keyword. They can optionally be preceded with the `pub` keyword, which defines
the class publicly, meaning it can be accessed from outside its defining module. A class contains zero or more parameters
and zero or more methods. All parameters are defined as public by default, while methods may be defined as either public
or private. A typical class declaration looks like this:
```
mod greeter

// Used by the `say_hi` method
import aura/io
```
{collapsible="true" collapsed-title="imports"}
```
// This class is called `Greeter` and is declared as public.
// It has one parameter, called `name` of type string, which must be
// passed in when creating an instance of this class
pub class Greeter(name: string) {
    pub fn say_hi() {
        // To access a class's parameters inside its declaration body,
        // the parameter name must be preceded by `this.`
        io.println("Hi, " + this.name)
    }
}
```

## Accessing Parameters and Methods

A class's parameters and methods can be accessed with dot notation on an instance of the class. Aura does not support
static class members, so something like this (using the above example class) will always be illegal: `Greeter.name`.
Instead, you would first create an instance of the class and then access its members, like this:
```
// Classes are instantiated as a method call, with the name of the class
// as the callee, and arguments corresponding to the class's parameters
g := Greeter("Bob")
// Once that's done, the programmer may access the class's members
g.say_hi()
```