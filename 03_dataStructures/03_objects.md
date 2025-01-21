# 🧳 Objects in JavaScript

Objects are used to store collections of data, and they are one of the most important data structures in JavaScript. Objects are key-value pairs, where keys are strings (or Symbols) and values can be any data type.

---

## 🔥 Creating Objects

You can create objects using **curly braces** `{}`, with key-value pairs separated by commas.

### Syntax:
```javascript
let objectName = {
  key1: value1,
  key2: value2
};
```

### Example: Creating an Object

```javascript
let car = {
  make: "Tesla",
  model: "Model 3",
  year: 2020
};
console.log(car);
```

### Output:
```
{
  make: "Tesla",
  model: "Model 3",
  year: 2020
}
```

---

## 🚀 Accessing Object Properties

You can access object properties using either dot notation or bracket notation.

### 1. **Dot Notation**
```javascript
objectName.key;
```

### Example: Accessing Properties with Dot Notation

```javascript
let car = {
  make: "Tesla",
  model: "Model 3",
  year: 2020
};
console.log(car.make);  // "Tesla"
```

### 2. **Bracket Notation**
```javascript
objectName["key"];
```

### Example: Accessing Properties with Bracket Notation

```javascript
let car = {
  make: "Tesla",
  model: "Model 3",
  year: 2020
};
console.log(car["model"]);  // "Model 3"
```

---

## 🧩 Modifying Object Properties

You can modify object properties by directly assigning a new value to the key.

### Example: Modifying Object Properties

```javascript
let car = {
  make: "Tesla",
  model: "Model 3",
  year: 2020
};
car.year = 2021;  // Changing the year
console.log(car);
```

### Output:
```
{
  make: "Tesla",
  model: "Model 3",
  year: 2021
}
```

---

## 🚀 Adding New Properties to Objects

You can add new properties to an existing object using either dot or bracket notation.

### Example: Adding New Properties

```javascript
let car = {
  make: "Tesla",
  model: "Model 3",
  year: 2020
};
car.color = "red";  // Adding a new property
console.log(car);
```

### Output:
```
{
  make: "Tesla",
  model: "Model 3",
  year: 2020,
  color: "red"
}
```

---

## 🧑‍💻 Example: Nested Objects

Objects can also contain other objects (nested objects), which allows for more complex data structures.

### Example: Nested Objects

```javascript
let car = {
  make: "Tesla",
  model: "Model 3",
  year: 2020,
  owner: {
    name: "John Doe",
    age: 30
  }
};
console.log(car.owner.name);  // "John Doe"
```

### Output:
```
John Doe
```

---

## 🚀 Object Methods

Objects can also contain functions, which are called **methods**. These methods can perform operations using the object’s properties.

### Example: Object with Methods

```javascript
let car = {
  make: "Tesla",
  model: "Model 3",
  year: 2020,
  startEngine: function() {
    console.log("Engine started");
  }
};
car.startEngine();  // Calling the method
```

### Output:
```
Engine started
```

---

## 💡 Key Takeaways
1. **Creating Objects**: Objects are created using curly braces `{}` with key-value pairs.
2. **Accessing Properties**: Use dot notation or bracket notation to access object properties.
3. **Modifying Objects**: Modify properties by assigning new values directly.
4. **Adding Properties**: You can add new properties to an object at any time.
5. **Nested Objects**: Objects can contain other objects.
6. **Methods**: Objects can have functions as methods to perform operations.

---

### 🔗 Resources
- [MDN: Object](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object)
- [JavaScript.info: Objects](https://javascript.info/object)

---

### 🎉 Recap
Objects are a fundamental data structure in JavaScript, allowing you to group related data together in key-value pairs. You can easily access, modify, and add properties, and even nest objects within each other for more complex structures.
