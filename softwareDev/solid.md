# SOLID principles

SOLID principles are principles, not rules. Make sure not to overfragment, use SOLID to assure maintainability, use it as a tool, not a goal.

## S - Single responsibility principle (SRP)

One class should be doing one thing or be responsible for only one thing.

Example:
If we are building a social media website with users, events, messages, etc... The user part of the system has nothing to do with the part responsible for creating events pages or displaying messages so it is better to separate them into different parts with their own responsibilities.


## O - Open/Closed principle (OCP)

**Open for extension but closed for modification.**

Desiging your software so that we can extend a class' behaviour without modifying it.

* Open for extension: A class' behavior can be extended.
* Closed for modification: No changes are allowed in the code.

### How?
**Abstractions.**

If we have a system that needs to work with different types of vehicles (Car, Bus, Motorcycle), in order to implement OCP, we would need to introduce a *Vehicle* interface/class.
We would then inject that *Vehicle* instance.

This way we could add new vehicles without having to change the dependent classes code.


## L - Liskov Substitution Principle

Every part of the code should get the expected result no matter what instance of a class it gets, given it implements the same interface.

A subclass should override the parent class methods in a way that does not break functionality from a client’s point of view.


## I - Interface Segregation Principle

A client should never be forced to depend on methods it doesn't use.

Breaking down interfaces by roles rather than by type favors *composition over inheritance* and *Decoupling over Coupling*.

Example:
Consider an interface called `Animal` which would have `eat`, `sleep`, `walk` methods. Some animals `fly` so inheriting from the monolith `Animal` would mean there are methods we might not use. Instead we could break into smaller interfaces by **roles** so our animal that flies could just use the `canEat` interface for example.


## D - Dependency inversion principle

High level modules should not depend on low level modules, they should depend on abstractions.
