# 💡 Introduction to Object-Oriented Programming (OOP)

Object-Oriented Programming (OOP) is a programming paradigm that organizes data and behavior into reusable structures called **objects**. OOP enables you to model real-world entities and relationships through classes, objects, inheritance, and more. It emphasizes modularity, scalability, and maintainability.

---

## 🛠️ Key Concepts in OOP

### 1. **Objects**
   - An **object** is a collection of related data and methods. Objects can represent real-world entities like a person, car, or bank account.
   - In JavaScript, objects are collections of properties (key-value pairs).

   ```javascript
   const person = {
     name: 'John',
     age: 30,
     greet: function() {
       console.log(`Hello, my name is ${this.name}`);
     }
   };
   ```

### 2. **Classes**
   - A **class** is a blueprint for creating objects. It defines the structure (properties) and behavior (methods) that objects created from the class will have.
   - Classes were introduced in ES6 to simplify the process of object creation and inheritance.

   ```javascript
   class Person {
     constructor(name, age) {
       this.name = name;
       this.age = age;
     }

     greet() {
       console.log(`Hello, my name is ${this.name}`);
     }
   }

   const person1 = new Person('Alice', 25);
   ```

---

## 🚀 Principles of Object-Oriented Programming

OOP is built on several key principles that promote code reuse, organization, and efficiency.

### 1. **Encapsulation**
   - Encapsulation refers to bundling the data (properties) and methods (functions) that operate on the data into a single unit, known as a class or object.
   - It restricts direct access to certain details of an object, allowing only controlled access through methods (getters and setters).

   Example:

   ```javascript
   class BankAccount {
     constructor(balance) {
       this._balance = balance;  // Private property
     }

     getBalance() {
       return this._balance;
     }

     deposit(amount) {
       this._balance += amount;
     }
   }

   const account = new BankAccount(100);
   account.deposit(50);
   console.log(account.getBalance());  // Output: 150
   ```

### 2. **Abstraction**
   - Abstraction is the concept of hiding the complex implementation details and exposing only the essential features of an object or class.
   - It helps in focusing on the object’s functionality without worrying about the internal workings.

   Example:

   ```javascript
   class Car {
     startEngine() {
       console.log("Engine started");
     }

     drive() {
       console.log("Driving the car");
     }
   }

   const myCar = new Car();
   myCar.startEngine();  // You don't need to know how the engine works internally
   myCar.drive();        // You only interact with the high-level methods
   ```

### 3. **Inheritance**
   - Inheritance allows one class (child) to inherit the properties and methods from another class (parent).
   - It promotes code reuse and creates hierarchical relationships between objects.

   Example:

   ```javascript
   class Animal {
     speak() {
       console.log("Animal speaks");
     }
   }

   class Dog extends Animal {
     speak() {
       console.log("Woof! Woof!");
     }
   }

   const dog = new Dog();
   dog.speak();  // Output: Woof! Woof!
   ```

### 4. **Polymorphism**
   - Polymorphism allows objects to be treated as instances of their parent class. It enables methods to be used in different ways depending on the object that calls them.

   Example:

   ```javascript
   class Shape {
     draw() {
       console.log("Drawing a shape");
     }
   }

   class Circle extends Shape {
     draw() {
       console.log("Drawing a circle");
     }
   }

   const shape = new Shape();
   const circle = new Circle();

   shape.draw();  // Output: Drawing a shape
   circle.draw(); // Output: Drawing a circle
   ```

---

## 💡 Benefits of Object-Oriented Programming

1. **Modularity**: OOP allows you to break down complex programs into smaller, manageable chunks (objects and classes).
2. **Reusability**: Classes and objects can be reused in different parts of your program or across different projects.
3. **Maintainability**: By organizing your code into objects, it’s easier to modify or extend the system without affecting other parts.
4. **Abstraction**: It hides unnecessary details and only exposes what is necessary for the user.
5. **Scalability**: OOP allows your codebase to grow with minimal friction. As requirements evolve, you can extend and modify classes without breaking existing functionality.

---

### 📝 Recap

- **OOP** is a paradigm that helps organize and model data, making it more manageable and maintainable.
- The key principles of OOP include **Encapsulation**, **Abstraction**, **Inheritance**, and **Polymorphism**.
- JavaScript provides built-in support for OOP concepts via **objects**, **classes**, and inheritance mechanisms.

---

## 🔗 Resources

- [MDN: Introduction to OOP](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Introduction)
- [JavaScript Classes - MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Classes)
