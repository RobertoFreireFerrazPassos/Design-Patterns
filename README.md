# Design-Patterns

____________________________________


**Creational patterns** provide object creation mechanisms that increase flexibility and reuse of existing code.

**Structural patterns** explain how to assemble objects and classes into larger structures, while keeping these structures flexible and efficient.

**Behavioral patterns** take care of effective communication and the assignment of responsibilities between objects.


____________________________________



## Creational patterns


____________________________________


## Structural patterns

### Decorator

The Decorator Pattern attaches additional responsibilities to an object dynamically.
Decorators provide a flexible alternative to subclassing for extending functionality.

<p align="center">
  <img src="https://github.com/RobertoFreireFerrazPassos/Design-Patterns/blob/main/img/decorator1.png?raw=true">
</p>


____________________________________



## Behavioral patterns

### Observer

The Observer Pattern defines a one-to-many dependency between objects so that when one object changes state, all of its dependents are notified and updated automatically.

<p align="center">
  <img src="https://github.com/RobertoFreireFerrazPassos/Design-Patterns/blob/main/img/observer1.PNG?raw=true">
</p>

**Principle: Identify the aspects of your application that vary and separate them from what stays the same.**
```
The thing that varies in the Observer Pattern is the state of the Subject and the number and types of Observers. 
With this pattern, you can vary the objects that are dependent on the state of the Subject, without having to change that Subject. That’s called planning ahead!
```

**Principle: Program to an interface, not an implementation.**
```
Both the Subject and Observers use interfaces.

Loosely Coupled Design.
Strive for loosely coupled designs between objects that interact.
Changes to either the subject or an observer will not affect the other.
Any changes to either are possible as long as they implement the Subject and Observer interfaces.
Before, the subject knew the implementation of the observers.
Now, We don’t need to make any changes to the subject to accommodate new classes (that implements observers).
The subject doesn’t care, it will deliver notifications to any object that implements the
Observer interface.
```

**Principle: Favor composition over inheritance**
```
The Observer Pattern uses composition to compose any number of Observers with their Subject.
These relationships aren’t set up by some kind of inheritance hierarchy. No, they are set up at runtime by composition!
We can add/remove observers at runtime.
```

<p align="center">
  <img src="https://github.com/RobertoFreireFerrazPassos/Design-Patterns/blob/main/img/observer2.PNG?raw=true">
</p>

### Template Method

The Template Method Pattern defines the skeleton of an algorithm in a method, deferring some steps to subclasses. 

Template Method lets subclasses redefine certain steps of an algorithm without changing the algorithm’s structure.

<p align="center">
  <img src="https://github.com/RobertoFreireFerrazPassos/Design-Patterns/blob/main/img/templatemethod.png?raw=true">
</p>

**Principle: Hollywood**
```
Hollywood Principle which states: "Don't Call Us, We'll Call You." 
It's closely related to the Dependency Inversion Principle.
The template method call the algorithm methods in the subclass, no the opposite.
```


____________________________________ 



References:

https://refactoring.guru/design-patterns

Book Head First Design Patterns: A Brain-Friendly Guide
