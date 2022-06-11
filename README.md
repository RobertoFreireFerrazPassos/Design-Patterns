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

#### Observer

The Observer Pattern defines a one-to-many dependency between objects so that when one object changes state, all of its dependents are notified and updated automatically.

<p align="center">
  <img src="https://github.com/RobertoFreireFerrazPassos/Design-Patterns/blob/main/img/observer1.PNG?raw=true">
</p>

**Loosely Coupled Principle**
```
Strive for loosely coupled designs between objects that interact.
Changes to either the subject or an observer will not affect the other.
Any changes to either are possible as long as they implement the Subject and Observer interfaces.
Before, the subject knew the implementation of the observers.
We don’t need to make any changes to the subject to accommodate new classes (that implements observers).
The subject doesn’t care, it will deliver notifications to any object that implements the
Observer interface.
```

Now, we can add/remove observers at runtime.

<p align="center">
  <img src="https://github.com/RobertoFreireFerrazPassos/Design-Patterns/blob/main/img/observer2.PNG?raw=true">
</p>

#### Template Method

The Template Method Pattern defines the skeleton of an algorithm in a method, deferring some steps to subclasses. 

Template Method lets subclasses redefine certain steps of an algorithm without changing the algorithm’s structure.

<p align="center">
  <img src="https://github.com/RobertoFreireFerrazPassos/Design-Patterns/blob/main/img/templatemethod.png?raw=true">
</p>

**Hollywood Principle**
```
Hollywood Principle which states: "Don't Call Us, We'll Call You." 
It's closely related to the Dependency Inversion Principle.
The template method call the algorithm methods in the subclass, no the opposite.
```
___________________________ 

References:

https://refactoring.guru/design-patterns

Book Head First Design Patterns: A Brain-Friendly Guide
