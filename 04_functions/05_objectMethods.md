# 🧑‍💻 Object Methods in JavaScript

In JavaScript, **object methods** are functions that are stored as properties of an object. They allow objects to perform actions, process data, or return a result. Object methods are an essential part of object-oriented programming in JavaScript.

---

## 🔥 What is an Object Method?

An **object method** is simply a function that is defined within an object. It can access and modify the object's properties and perform various tasks based on the data inside the object.

---

## 🚀 Defining Object Methods

You can define methods in objects in a few different ways.

### Example: Method Defined Using a Function Expression

```javascript
const person = {
  firstName: "John",
  lastName: "Doe",
  fullName: function() {
    return this.firstName + " " + this.lastName;
  }
};

console.log(person.fullName());  // Output: John Doe
```

In this example, `fullName` is a method of the `person` object.

---

## 🧩 Method Shorthand Syntax (ES6+)

In ES6 and later, JavaScript allows a shorthand syntax for defining object methods. This approach does not require the `function` keyword.

### Example: Shorthand Method Syntax

```javascript
const person = {
  firstName: "Alice",
  lastName: "Smith",
  fullName() {
    return this.firstName + " " + this.lastName;
  }
};

console.log(person.fullName());  // Output: Alice Smith
```

### Output:
```
Alice Smith
```

---

## 🚀 `this` Keyword in Object Methods

In the context of object methods, the **`this` keyword** refers to the object the method belongs to. It allows the method to access the object's properties and other methods.

### Example: Using `this` Inside a Method

```javascript
const car = {
  make: "Toyota",
  model: "Corolla",
  year: 2020,
  displayInfo() {
    return `${this.year} ${this.make} ${this.model}`;
  }
};

console.log(car.displayInfo());  // Output: 2020 Toyota Corolla
```

### Output:
```
2020 Toyota Corolla
```

Here, `this` refers to the `car` object, allowing the method to access its properties.

---

## 🧩 `Object.create()` Method

The **`Object.create()`** method creates a new object, using an existing object as the prototype for the new object. This is useful when you want to create an object with specific properties or methods.

### Example: Using `Object.create()`

```javascript
const animal = {
  makeSound() {
    console.log("Animal makes a sound");
  }
};

const dog = Object.create(animal);
dog.bark = function() {
  console.log("Woof! Woof!");
};

dog.makeSound();  // Output: Animal makes a sound
dog.bark();       // Output: Woof! Woof!
```

### Output:
```
Animal makes a sound
Woof! Woof!
```

---

## 🚀 `Object.assign()` Method

The **`Object.assign()`** method copies the values of all enumerable properties from one or more source objects to a target object. It is often used to merge objects.

### Example: Using `Object.assign()`

```javascript
const person = {
  name: "John",
  age: 30
};

const job = {
  role: "Developer",
  company: "ABC Corp"
};

const employee = Object.assign({}, person, job);

console.log(employee);  // Output: { name: "John", age: 30, role: "Developer", company: "ABC Corp" }
```

### Output:
```
{ name: "John", age: 30, role: "Developer", company: "ABC Corp" }
```

---

## 🧩 `Object.keys()` Method

The **`Object.keys()`** method returns an array of a given object's own property names (keys), in the same order as that provided by a `for...in` loop.

### Example: Using `Object.keys()`

```javascript
const person = {
  name: "Sarah",
  age: 28,
  occupation: "Engineer"
};

const keys = Object.keys(person);
console.log(keys);  // Output: ["name", "age", "occupation"]
```

### Output:
```
["name", "age", "occupation"]
```

---

## 🚀 `Object.values()` Method

The **`Object.values()`** method returns an array of a given object's own property values, in the same order as `Object.keys()`.

### Example: Using `Object.values()`

```javascript
const person = {
  name: "Sarah",
  age: 28,
  occupation: "Engineer"
};

const values = Object.values(person);
console.log(values);  // Output: ["Sarah", 28, "Engineer"]
```

### Output:
```
["Sarah", 28, "Engineer"]
```

---

## 🧩 `Object.entries()` Method

The **`Object.entries()`** method returns an array of an object's own enumerable string-keyed property `[key, value]` pairs.

### Example: Using `Object.entries()`

```javascript
const person = {
  name: "John",
  age: 30
};

const entries = Object.entries(person);
console.log(entries);  // Output: [["name", "John"], ["age", 30]]
```

### Output:
```
[["name", "John"], ["age", 30]]
```

---

## 🚀 `Object.freeze()` Method

The **`Object.freeze()`** method freezes an object, preventing new properties from being added and existing properties from being modified or deleted.

### Example: Using `Object.freeze()`

```javascript
const person = {
  name: "Mike",
  age: 25
};

Object.freeze(person);

person.age = 30;  // This will not change the age property
person.city = "New York";  // This will not add a new property

console.log(person);  // Output: { name: "Mike", age: 25 }
```

### Output:
```
{ name: "Mike", age: 25 }
```

---

## 💡 Key Takeaways
1. **Object Methods**: Functions that are properties of an object, allowing you to interact with the object’s data.
2. **`this` Keyword**: Refers to the object the method belongs to, enabling access to its properties.
3. **`Object.create()`**: Creates a new object based on an existing one.
4. **`Object.assign()`**: Copies properties from one or more objects to a target object.
5. **`Object.keys()`**: Returns an array of the object's keys.
6. **`Object.values()`**: Returns an array of the object's values.
7. **`Object.entries()`**: Returns an array of `[key, value]` pairs from the object.
8. **`Object.freeze()`**: Prevents changes to an object (immutability).

---

### 🔗 Resources
- [MDN: Object Methods](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object)
- [JavaScript.info: Object Methods](https://javascript.info/object-methods)

---

### 🎉 Recap
Object methods are functions tied to objects that allow manipulation and interaction with their properties. With methods like `Object.assign()`, `Object.keys()`, and `Object.entries()`, JavaScript offers powerful tools for working with objects and their data. Understanding how to define and use these methods is crucial for effective object-oriented programming.

