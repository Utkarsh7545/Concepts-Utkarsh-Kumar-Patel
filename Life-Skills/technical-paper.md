# SOLID 

SOLID is a set of five guidelines to make code more maintainable, scalable, and understandable. SOLID is an acronym for the first five object-oriented design (OOD) principles. Below is an overview of each principle with code examples.


### 1. Single Responsibility Principle (SRP)

Each class should have one, and only one, reason to change. This means that a class should have only one job.

#### Example:
```
// Before: Handles both invoice and printing
class Invoice {
  printInvoice() {}
  calculateTotal() {}
}

// After: Separated into two classes
class Invoice {
  calculateTotal() {}
}
class InvoicePrinter {
  printInvoice() {}
}
```


### 2. Open/Closed Principle (OCP)

Classes should be open for extension but closed for modification. You can extend functionality by adding new code, not changing existing code.

#### Example:
```
// Before: Modification of existing class
class Shape {
  draw() {}
  drawCircle() {}
  drawSquare() {}
}

// After: Extend functionality with subclasses
class Shape {
  draw() {}
}
class Circle extends Shape {
  draw() {}
}
class Square extends Shape {
  draw() {}
}
```


### 3. Liskov Substitution Principle (LSP)

Derived classes should be substitutable for their base classes without affecting the application.

#### Example:
```
// Before: Violation of LSP
class Bird {
  fly() {}
}
class Penguin extends Bird {
  fly() { throw 'Penguins can’t fly!'; }
}

// After: Fixed LSP
class Bird {
  move() {}
}
class Penguin extends Bird {
  move() {}
}
```


### 4. Interface Segregation Principle (ISP)

Clients should not be forced to implement interfaces they don’t use. Break down large interfaces into smaller, more specific ones.

#### Example:
```
// Before: Large interface
interface Worker {
  work();
  eat();
}

// After: Segregated interfaces
interface Workable {
  work();
}
interface Eatable {
  eat();
}
```


### 5. Dependency Inversion Principle (DIP)

High-level modules should not depend on low-level modules. Both should depend on abstractions.

#### Example:
```
// Before: Direct dependency on low-level module
class LightBulb {
  turnOn() {}
}
class Switch {
  constructor() {
    this.bulb = new LightBulb();
  }
}

// After: Depend on abstraction
class LightSource {
  turnOn() {}
}
class Switch {
  constructor(lightSource) {
    this.lightSource = lightSource;
  }
}
```


## Conclusion

Following SOLID principles makes the codebase more manageable, scalable, and easier to maintain. By implementing SRP, OCP, LSP, ISP, and DIP, we can refactor the code efficiently.


## References

[SOLID Principles Explained](https://www.digitalocean.com/community/conceptual-articles/s-o-l-i-d-the-first-five-principles-of-object-oriented-design)
[SOLID Principles Playlist](https://www.youtube.com/playlist?list=PL6n9fhu94yhXjG1w2blMXUzyDrZ_eyOme)

