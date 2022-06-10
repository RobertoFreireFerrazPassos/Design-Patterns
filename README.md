## Design-Patterns

___________________________

**Creational patterns** provide object creation mechanisms that increase flexibility and reuse of existing code.

**Structural patterns** explain how to assemble objects and classes into larger structures, while keeping these structures flexible and efficient.

**Behavioral patterns** take care of effective communication and the assignment of responsibilities between objects.

___________________________

### Creational patterns
___________________________

### Structural patterns

___________________________

### Behavioral patterns

#### Template Method

The Template Method Pattern defines the skeleton of an algorithm in a method, deferring some steps to subclasses. 
Template Method lets subclasses redefine certain steps of an algorithm without changing the algorithm’s structure.

<p align="center">
  <img src="https://github.com/RobertoFreireFerrazPassos/dotNet-OOP/blob/main/images/templatemethod.png?raw=true">
</p>

It uses **Hollywood Principle** which states, "Don't Call Us, We'll Call You.". It's closely related to the Dependency Inversion Principle.
The template method call the algorithm methods in the subclass, no the opposite.
___________________________ 

References:

https://refactoring.guru/design-patterns

Book Head First Design Patterns: A Brain-Friendly Guide
