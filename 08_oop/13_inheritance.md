# 🧬 Inheritance in JavaScript

**Inheritance** is a fundamental concept in Object-Oriented Programming (OOP) that allows a class (or object) to inherit properties and methods from another class (or object). In JavaScript, inheritance enables the creation of new objects based on existing ones, promoting code reuse and modularity.

In JavaScript, inheritance is achieved through prototypes, allowing objects to share properties and methods.

---

## 🔑 What is Inheritance?

Inheritance allows one object (or class) to inherit properties and methods from another. This helps eliminate redundancy and creates a hierarchical relationship between classes. In JavaScript, this can be achieved by using **prototypes** or **class-based inheritance**.

### Types of Inheritance in JavaScript:
- **Prototype-based inheritance**: Every object in JavaScript has an internal property `[[Prototype]]` (accessed using `Object.getPrototypeOf()`), which points to another object. This allows objects to inherit properties and methods from their prototypes.
- **Class-based inheritance (ES6)**: The `class` syntax introduced in ES6 allows for a more familiar way of setting up inheritance, similar to other object-oriented languages.

---

## 🧑‍🏫 Example: Prototype-based Inheritance

In JavaScript, inheritance can be implemented through prototypes. Here's an example of how objects inherit properties and methods from other objects.

```javascript
function Animal(name) {
  this.name = name;
}

Animal.prototype.speak = function() {
  console.log(`${this.name} makes a noise.`);
};

function Dog(name) {
  Animal.call(this, name);  // Inherit properties from Animal
}

// Set up inheritance
Dog.prototype = Object.create(Animal.prototype);
Dog.prototype.constructor = Dog;

// Override the speak method
Dog.prototype.speak = function() {
  console.log(`${this.name} barks.`);
};

let dog = new Dog("Rex");
dog.speak();  // Rex barks.
```

In this example:
- The `Dog` class inherits from the `Animal` class by setting the `Dog.prototype` to an object created from `Animal.prototype`.
- The `Dog` class can now access the `speak()` method from the `Animal` prototype but can also override it with its own version.

---

## 👨‍🏫 Example: Class-based Inheritance (ES6)

With the introduction of ES6, JavaScript now supports **class-based inheritance** which is more syntactically similar to other OOP languages.

```javascript
class Animal {
  constructor(name) {
    this.name = name;
  }

  speak() {
    console.log(`${this.name} makes a noise.`);
  }
}

class Dog extends Animal {
  constructor(name) {
    super(name);  // Call the parent class constructor
  }

  speak() {
    console.log(`${this.name} barks.`);
  }
}

let dog = new Dog("Rex");
dog.speak();  // Rex barks.
```

In this example:
- The `Dog` class extends the `Animal` class using the `extends` keyword.
- The `super()` method is used to call the constructor of the parent class, allowing the `Dog` class to inherit the `name` property.
- The `speak()` method is overridden in the `Dog` class, just like in the previous example.

---

## 🚀 Real-World Example: Vehicle Inheritance

Let's consider a real-world scenario where we have a **Vehicle** class, and we want to create a **Car** class that inherits from **Vehicle**.

### Prototype-based Inheritance Example:

```javascript
function Vehicle(type, brand) {
  this.type = type;
  this.brand = brand;
}

Vehicle.prototype.displayInfo = function() {
  console.log(`This is a ${this.type} from ${this.brand}.`);
};

function Car(brand, model) {
  Vehicle.call(this, "Car", brand);  // Inherit properties from Vehicle
  this.model = model;
}

Car.prototype = Object.create(Vehicle.prototype);
Car.prototype.constructor = Car;

Car.prototype.displayCarInfo = function() {
  console.log(`This car is a ${this.brand} ${this.model}.`);
};

let car = new Car("Toyota", "Corolla");
car.displayInfo();           // This is a Car from Toyota.
car.displayCarInfo();       // This car is a Toyota Corolla.
```

### Class-based Inheritance Example:

```javascript
class Vehicle {
  constructor(type, brand) {
    this.type = type;
    this.brand = brand;
  }

  displayInfo() {
    console.log(`This is a ${this.type} from ${this.brand}.`);
  }
}

class Car extends Vehicle {
  constructor(brand, model) {
    super("Car", brand);
    this.model = model;
  }

  displayCarInfo() {
    console.log(`This car is a ${this.brand} ${this.model}.`);
  }
}

let car = new Car("Toyota", "Corolla");
car.displayInfo();           // This is a Car from Toyota.
car.displayCarInfo();       // This car is a Toyota Corolla.
```

In both examples:
- The **Car** class inherits from the **Vehicle** class.
- The **Car** class can access the `displayInfo()` method from the **Vehicle** class, and it can also define its own specific method, `displayCarInfo()`.

---

## 🛠️ Key Points About Inheritance

- **Code Reusability**: Inheritance allows objects or classes to reuse code from other objects or classes, reducing redundancy and improving maintainability.
- **Hierarchical Relationships**: Inheritance establishes a "is-a" relationship, where a subclass is a type of the superclass.
- **Overriding Methods**: A subclass can override methods from the superclass to provide a more specific implementation.
- **Super Keyword**: In class-based inheritance, the `super()` method is used to call the constructor and methods of the parent class.

---

## 💡 Conclusion

Inheritance is a powerful feature of OOP that promotes code reuse and allows the creation of hierarchical relationships between objects and classes. In JavaScript, inheritance can be implemented using either **prototype-based inheritance** or **class-based inheritance**.

By leveraging inheritance, you can create modular, maintainable, and scalable code that can easily be extended as your application grows.

---

## 📚 Resources

- [MDN - Class Inheritance](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Classes#Inheritance)
- [JavaScript.info - Inheritance](https://javascript.info/class-inheritance)
