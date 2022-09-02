# Design-Patterns

____________________________________

<details>
<summary style="font-size:14px">Object-Oriented Principles</summary>
<p>

Encapsulate what varies.

Favor composition over inheritance.

Program to interfaces, not implementations.

Strive for loosely coupled designs between objects that interact.

Classes should be open for extension but closed for modification.

Depend on abstractions. Do not depend on concrete classes.

Only talk to your friends.

Don’t call us, we’ll call you.

A class should have only one reason to change.

</p></details>

____________________________________

**Behavioral patterns** take care of effective communication and the assignment of responsibilities between objects.

**Creational patterns** provide object creation mechanisms that increase flexibility and reuse of existing code.

**Structural patterns** explain how to assemble objects and classes into larger structures, while keeping these structures flexible and efficient.

____________________________________ 

## Behavioral patterns

<details>
<summary style="font-size:14px">Strategy</summary>
<p>

The Strategy Pattern defines a family of algorithms, encapsulates each one, and makes them interchangeable. Strategy lets the algorithm vary independently from clients that use it.

- We wanna add quack and fly behaviours in a duck. 
- At first, it seems a good idea to add fly and quack methods in the superclass. We will have reuse of code.
- But, everytime we wanna implement a new duck, we must override the superclass method if we wanna remove/change a behaviour. Ex: a duck which it doesn't fly. Otherwise, a duck can have a behavior that it is not supposed to have. 
- Also, the fly and quack behaviours of ducks can change. We don't wanna have to change in all subclasses that override a specific behaviour everytime it changes. Not reuse of code. 

Also, we are gonna apply the principle **Encapsulate what varies.** (Take what varies and “encapsulate” it so it won’t affect the rest of your code. It is also good for reuse of code).

We are gonna apply the principle **Program to an interface, not an implementation.** (the Duck classes won’t need to know any of the implementation details for their own behaviors.)

<p align="center">
  <img src="https://github.com/RobertoFreireFerrazPassos/Design-Patterns/blob/main/img/strategy2.png?raw=true">
</p>

Also, we are gonna apply the principle **Favor composition over inheritance** (Inheritance creates structure while composition creates flexibility)

The HAS-A relationship is an interesting one: each duck has a FlyBehavior and a QuackBehavior to which it delegates flying and quacking. 

Creating systems using composition gives you a lot more flexibility. Not only does it let you encapsulate a family of algorithms into their own set of classes, but it also lets you change behavior at runtime as long as the object you’re composing with implements the correct behavior interface.

Final result:

<p align="center">
  <img src="https://github.com/RobertoFreireFerrazPassos/Design-Patterns/blob/main/img/strategy1.png?raw=true">
</p>

</p></details>

<details>
<summary style="font-size:14px">Observer</summary>
<p>

The Observer Pattern defines a one-to-many dependency between objects so that when one object changes state, all of its dependents are notified and updated automatically.

<p align="center">
  <img src="https://github.com/RobertoFreireFerrazPassos/Design-Patterns/blob/main/img/observer1.PNG?raw=true">
</p>

**Principle: Encapsulate what varies.**

The thing that varies in the Observer Pattern is the state of the Subject and the number and types of Observers. 
With this pattern, you can vary the objects that are dependent on the state of the Subject, without having to change that Subject. That’s called planning ahead!


**Principle: Program to an interface, not an implementation.**

Both the Subject and Observers use interfaces.
Strive for loosely coupled designs between objects that interact.
Changes to either the subject or an observer will not affect the other.
Any changes to either are possible as long as they implement the Subject and Observer interfaces.
Before, the subject knew the implementation of the observers.
Now, We don’t need to make any changes to the subject to accommodate new classes (that implements observers).
The subject doesn’t care, it will deliver notifications to any object that implements the
Observer interface.


**Principle: Favor composition over inheritance**

The Observer Pattern uses composition to compose any number of Observers with their Subject.
These relationships aren’t set up by some kind of inheritance hierarchy. No, they are set up at runtime by composition!
We can add/remove observers at runtime.


<p align="center">
  <img src="https://github.com/RobertoFreireFerrazPassos/Design-Patterns/blob/main/img/observer2.PNG?raw=true">
</p>

</p></details>

<details>
<summary style="font-size:14px">Template Method</summary>
<p>

The Template Method Pattern defines the skeleton of an algorithm in a method, deferring some steps to subclasses. Template Method lets subclasses redefine certain steps of an algorithm without changing the algorithm’s structure.

**Principle: Hollywood - "Don't Call Us, We'll Call You."**

It's closely related to the Dependency Inversion Principle.
The template method call the algorithm methods in the subclass, no the opposite.

For this design pattern, we **don't** favor composition over inheritance. We don't wanna flexibility in the template function. We wanna structure. The beverage subclasses must always follow the same algorithm provided in the base class as a template. But, each subclass can define or redefine each primitive operation, depending on how the base class have defined the primitive operations (abstract, non-abstract or virtual) 

<p align="center">
  <img src="https://github.com/RobertoFreireFerrazPassos/Design-Patterns/blob/main/img/templatemethod.png?raw=true">
</p>

</p></details>

____________________________________

## Creational patterns

<details>
<summary style="font-size:14px">Factory Method</summary>
<p>

The Factory Method Pattern defines an interface for creating an object, but lets subclasses decide which class to instantiate. 

Factory Method lets a class defer instantiation to subclasses.

**Principle: Encapsulate what varies.**

All the decision on creation of a pizza by style and type varies, so we did encapsulate this logic in the CreatePizza Method

**Principle: Classes should be open for extension but closed for modification.**

We used inheritance with PizzaStore, so everytime we add a new style of PizzaStore, we don't need to change the CreatePizza method. So, the CreatePizza method is closed for modification, but open for extension by its childs (ChicagoPizzaStore,NYPizzaStore,...)

**Depend on abstractions. Do not depend on concrete classes.**

We are depending on the abstractions, Pizza (Product) and PizzaStore (Creator).

<p align="center">
  <img src="https://github.com/RobertoFreireFerrazPassos/Design-Patterns/blob/main/img/factorymethod1.png?raw=true">
</p>

</p></details>

<details>
<summary style="font-size:14px">Abstract Factory</summary>
<p>

Abstract Factory Pattern provides an interface for creating families of related or dependent objects without specifying their concrete classes.

<p align="center">
  <img src="https://github.com/RobertoFreireFerrazPassos/Design-Patterns/blob/main/img/factorymethod2.png?raw=true">
</p>
</p></details>

____________________________________

## Structural patterns

<details>
<summary style="font-size:14px">Decorator</summary>
<p>

The Decorator Pattern attaches additional responsibilities to an object dynamically.
Decorators provide a flexible alternative to subclassing for extending functionality.

Decorator is a **wrapper**. A wrapper is an object that can be linked with some target object. The wrapper contains the same set of methods as the target and delegates to it all requests it receives. However, the wrapper may alter the result by doing something either before or after it passes the request to the target.

**Principle: Favor composition over inheritance**

It uses composition to wrap the object and it uses inheritance to achieve the type matching.

Using only inheritance, like in the code "before" example, we have code duplication.

In this example, if we want a new ThincrustPizzaWithOlives, we would have to to create a duplication of class ThickcrustPizzaWithOlives with only difference that it would inherits from ThincrustPizza instead of ThickcrustPizza. 

With composition, we don't need to duplicate the logic for olives, we can have ThickcrustPizza, ThincrustPizza and the Olives (Decorator class) separately. Olives will wraps the pizza (ThickcrustPizza, ThincrustPizza,...) by composition and since it inherits Pizza through ToppingDecorator, it will also overide the pizza behaviors. So, we have flexibility by using composition.

With Composition, we can use Cheese to add responsibilities to ThickcrustPizza dynamically.


<p align="center">
  <img src="https://github.com/RobertoFreireFerrazPassos/Design-Patterns/blob/main/img/decorator1.png?raw=true">
</p>

</p></details>

____________________________________

## References:

https://refactoring.guru/design-patterns

Book Head First Design Patterns: A Brain-Friendly Guide
