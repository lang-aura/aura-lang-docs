# Structs

Structs in Aura are designed to contain data. They can be used in place of classes in situations where the programmer
needs to store data without providing any additional functionality on that data. This is in contrast to classes, which
can provide functionality in addition to storing data. A typical struct declaration would look like this:
```
struct ApiResponse(id: string, first_name: string, last_name: string, age: int)
```
A struct's declaration looks similar to a class, except a struct does not contain a body, since it is not permitted to
define any methods.

## Instances

A struct can be instantiated as a method call, with arguments passed in that correspond to each parameter, like so:
```
resp := ApiResponse("1", "John", "Doe", 20)
```
And from there, you can access the struct instance's parameters with typical dot notation:
```
resp.id // "1"
resp.first_name // "John"
resp.last_name // "Doe"
resp.age // 20
```