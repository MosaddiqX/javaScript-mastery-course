# 🧑‍💻 Function Types in JavaScript

In JavaScript, functions are not just basic building blocks, they can also take various forms. Understanding the different types of functions will help you write cleaner and more flexible code.

---

## 🔥 Function Declarations

As previously mentioned, **function declarations** are the most common way to define a function. These functions are hoisted, meaning they can be called before they are defined in the code.

### Syntax:
```javascript
function functionName() {
  // Code to execute
}
```

### Example: Function Declaration

```javascript
function greet() {
  console.log("Hello!");
}
greet();  // Calling the function
```

### Output:
```
Hello!
```

---

## 🚀 Function Expressions

**Function expressions** involve creating a function and assigning it to a variable. These functions are **not hoisted**, which means they cannot be called before their definition.

### Syntax:
```javascript
const functionName = function() {
  // Code to execute
};
```

### Example: Function Expression

```javascript
const greet = function() {
  console.log("Hello, world!");
};
greet();  // Calling the function
```

### Output:
```
Hello, world!
```

---

## 🧩 Arrow Functions

Arrow functions offer a more concise syntax for writing functions. They are especially useful for shorter functions and allow you to write cleaner code.

### Syntax:
```javascript
const functionName = (parameters) => {
  // Code to execute
};
```

### Example: Arrow Function

```javascript
const greet = () => {
  console.log("Hello, world!");
};
greet();  // Calling the function
```

### Output:
```
Hello, world!
```

---

### 🧩 Arrow Function with Parameters

Arrow functions can also accept parameters, just like regular functions.

```javascript
const greet = (name) => {
  console.log("Hello, " + name + "!");
};
greet("Alice");  // Calling the function with an argument
```

### Output:
```
Hello, Alice!
```

---

## 🚀 Implicit Return with Arrow Functions

If an arrow function only contains a single expression, you can **omit the curly braces** and the `return` keyword. This is called **implicit return**.

### Syntax:
```javascript
const functionName = (parameters) => expression;
```

### Example: Arrow Function with Implicit Return

```javascript
const add = (a, b) => a + b;
console.log(add(2, 3));  // 5
```

### Output:
```
5
```

---

## 🧑‍💻 Immediately Invoked Function Expressions (IIFE)

An **Immediately Invoked Function Expression (IIFE)** is a function that runs as soon as it is defined. This pattern is used to create a new scope for variables.

### Syntax:
```javascript
(function() {
  // Code to execute immediately
})();
```

### Example: IIFE

```javascript
(function() {
  console.log("This function runs immediately!");
})();
```

### Output:
```
This function runs immediately!
```

---

## 💡 Key Takeaways
1. **Function Declarations**: Standard way of defining functions, hoisted.
2. **Function Expressions**: Functions assigned to variables, not hoisted.
3. **Arrow Functions**: Shorter, cleaner syntax for functions.
4. **Implicit Return**: Arrow functions can return a value without curly braces and `return`.
5. **IIFE**: Functions that run immediately after they are defined.

---

### 🔗 Resources
- [MDN: Function Expressions](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/function)
- [JavaScript.info: Arrow Functions](https://javascript.info/arrow-functions)

---

### 🎉 Recap
In JavaScript, there are different ways to define functions. You can use **declarations**, **expressions**, or **arrow functions**. Each type has its own advantages, such as the concise syntax of arrow functions or the flexibility of immediately invoked functions (IIFE).

