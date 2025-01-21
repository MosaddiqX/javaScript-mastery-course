# 🔑 Access Modifiers in JavaScript

In Object-Oriented Programming (OOP), **access modifiers** are used to control the visibility and accessibility of properties and methods within classes. JavaScript, as of now, provides a way to implement **public** and **private** modifiers through class syntax, with some support for **protected** behavior using closures or other patterns.

---

## 🚪 Public Modifiers

By default, all properties and methods of a class in JavaScript are **public**. This means that they can be accessed and modified from outside the class.

### Example of Public Methods and Properties

```javascript
class Person {
  constructor(name, age) {
    this.name = name;  // Public property
    this.age = age;    // Public property
  }

  greet() {
    console.log(`Hello, my name is ${this.name} and I am ${this.age} years old.`);
  }
}

let person = new Person('Alice', 30);
console.log(person.name); // Output: Alice
person.greet();           // Output: Hello, my name is Alice and I am 30 years old.
```

In this example:
- `name` and `age` are **public** properties.
- `greet()` is a **public** method.

---

## 🔒 Private Modifiers (ES2022+)

In JavaScript, **private** members are properties and methods that cannot be accessed from outside the class. As of ES2022, JavaScript introduced private fields and methods using the `#` syntax.

### Example of Private Fields

```javascript
class Person {
  #name;   // Private property
  #age;    // Private property

  constructor(name, age) {
    this.#name = name;
    this.#age = age;
  }

  getName() {
    return this.#name;  // Access private property through method
  }

  getAge() {
    return this.#age;   // Access private property through method
  }
}

let person = new Person('Bob', 40);
console.log(person.getName()); // Output: Bob
console.log(person.getAge());  // Output: 40

// Trying to access private fields directly will throw an error
// console.log(person.#name);  // SyntaxError: Private field '#name' must be declared in an enclosing class
```

In this example:
- `#name` and `#age` are **private** properties.
- These private members cannot be accessed directly from outside the class.
- To access the private properties, we use public getter methods like `getName()` and `getAge()`.

---

## 🔐 Simulating Private with Closures

Before private fields were introduced in JavaScript, private members were simulated using **closures**. A common approach was to define private variables inside the constructor function.

### Example of Private Members Using Closures

```javascript
function Person(name, age) {
  let _name = name;  // Private variable
  let _age = age;    // Private variable

  this.getName = function() {
    return _name;
  };

  this.getAge = function() {
    return _age;
  };
}

let person = new Person('Charlie', 35);
console.log(person.getName());  // Output: Charlie
console.log(person.getAge());   // Output: 35

// Trying to access private members directly is not possible
// console.log(person._name);  // Undefined
```

In this example:
- `_name` and `_age` are private variables because they are not accessible from outside the constructor.
- The `getName()` and `getAge()` methods allow access to the private members.

---

## ⚙️ Protected Members (Simulation)

JavaScript doesn’t have an official `protected` keyword, but we can simulate **protected** members by using naming conventions and closures. **Protected** members are typically only accessible within the class and its subclasses (not from outside).

### Simulating Protected Members

```javascript
class Animal {
  constructor(name) {
    this._name = name;  // Protected member (by convention)
  }

  speak() {
    console.log(`${this._name} makes a sound.`);
  }
}

class Dog extends Animal {
  constructor(name, breed) {
    super(name);
    this._breed = breed;  // Protected member (by convention)
  }

  bark() {
    console.log(`${this._name} barks.`);
  }
}

let dog = new Dog('Rex', 'Bulldog');
dog.speak();   // Output: Rex makes a sound.
dog.bark();    // Output: Rex barks.
console.log(dog._name);   // Output: Rex (accessible but considered protected by convention)
```

In this example:
- `_name` and `_breed` are considered **protected** members by convention. They can be accessed within the class or subclass, but outside code should avoid using them directly.

---

## 🛠️ Access Modifiers in Practice

1. **Public** members can be accessed anywhere.
2. **Private** members (using `#`) can only be accessed within the class itself.
3. **Protected** members can be accessed within the class and its subclasses (simulated using conventions or closures).

---

## 📚 Resources

- [MDN - Class Fields and Methods](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Classes)
- [JavaScript.info - Private Fields](https://javascript.info/private-methods-fields)

---

## 🏅 Summary

- **Public** members are accessible from anywhere.
- **Private** members are encapsulated inside the class and can’t be accessed directly from outside.
- **Protected** members are intended to be used within the class and its subclasses (simulated with conventions in JavaScript).
- The `#` syntax allows defining **private fields** and **private methods** in JavaScript classes.

