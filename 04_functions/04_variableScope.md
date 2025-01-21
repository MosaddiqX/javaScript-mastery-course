# 🧑‍💻 Variable Scope in JavaScript

In JavaScript, **variable scope** refers to where a variable is accessible or visible in your code. Understanding the scope of variables is essential for managing your code and preventing unexpected behavior.

---

## 🔥 What is Scope?

**Scope** defines the accessibility of variables, functions, and objects in some particular part of the code during runtime. There are two main types of scope in JavaScript: **Global Scope** and **Local Scope**.

---

## 🚀 Global Scope

A variable has **global scope** if it is declared outside any function. This means the variable is accessible from anywhere in your code.

### Example: Global Scope

```javascript
let globalVar = "I'm a global variable";

function printGlobal() {
  console.log(globalVar);  // Accessing global variable inside a function
}

printGlobal();  // Output: I'm a global variable
console.log(globalVar);  // Output: I'm a global variable
```

### Output:
```
I'm a global variable
I'm a global variable
```

---

## 🧩 Local Scope

A variable has **local scope** if it is declared inside a function. It is only accessible within that function.

### Example: Local Scope

```javascript
function printLocal() {
  let localVar = "I'm a local variable";
  console.log(localVar);  // Accessing local variable inside the function
}

printLocal();  // Output: I'm a local variable
console.log(localVar);  // Error: localVar is not defined (because it's local)
```

### Output:
```
I'm a local variable
Uncaught ReferenceError: localVar is not defined
```

---

## 🚀 Function Scope (ES5)

In **ES5**, variables declared with the `var` keyword have **function scope**, meaning they are accessible within the function in which they are declared, even if they are declared inside a block.

### Example: Function Scope with `var`

```javascript
function testFunction() {
  if (true) {
    var functionVar = "I'm inside an if block, but still accessible outside";
  }
  console.log(functionVar);  // Output: I'm inside an if block, but still accessible outside
}

testFunction();
```

### Output:
```
I'm inside an if block, but still accessible outside
```

---

## 🧩 Block Scope (ES6+)

In **ES6** and later, variables declared with `let` or `const` are block-scoped. This means they are only accessible within the block, statement, or expression where they are defined.

### Example: Block Scope with `let`

```javascript
if (true) {
  let blockVar = "I'm block-scoped";
  console.log(blockVar);  // Output: I'm block-scoped
}

console.log(blockVar);  // Error: blockVar is not defined
```

### Output:
```
I'm block-scoped
Uncaught ReferenceError: blockVar is not defined
```

---

## 🚀 Lexical Scope

**Lexical scope** refers to the way JavaScript determines the scope of a variable based on where it is defined in the code. In simple terms, a function's scope is determined by its location in the code.

### Example: Lexical Scope

```javascript
function outerFunction() {
  let outerVar = "I'm in the outer function";

  function innerFunction() {
    console.log(outerVar);  // Inner function can access variables from the outer function
  }

  innerFunction();
}

outerFunction();
```

### Output:
```
I'm in the outer function
```

---

## 🧑‍💻 Scope Chain

When accessing a variable, JavaScript first checks the current function's scope. If it doesn’t find the variable there, it looks in the outer function’s scope, and so on. This is called the **scope chain**.

### Example: Scope Chain

```javascript
let globalVar = "I'm a global variable";

function outerFunction() {
  let outerVar = "I'm an outer variable";

  function innerFunction() {
    let innerVar = "I'm an inner variable";
    console.log(globalVar);  // Accessing global variable
    console.log(outerVar);   // Accessing outer variable
    console.log(innerVar);   // Accessing inner variable
  }

  innerFunction();
}

outerFunction();
```

### Output:
```
I'm a global variable
I'm an outer variable
I'm an inner variable
```

---

## 🚀 Hoisting

**Hoisting** is JavaScript’s default behavior of moving declarations to the top of their containing scope during the compile phase. However, only the declarations are hoisted, not the initializations.

### Example: Hoisting with `var`

```javascript
console.log(myVar);  // Output: undefined
var myVar = "Hoisted!";
```

### Output:
```
undefined
```

### Example: Hoisting with `let` and `const`

```javascript
console.log(myVar);  // Error: Cannot access 'myVar' before initialization
let myVar = "Hoisted!";
```

### Output:
```
Uncaught ReferenceError: Cannot access 'myVar' before initialization
```

---

## 💡 Key Takeaways
1. **Global Scope**: Variables declared outside any function are accessible everywhere.
2. **Local Scope**: Variables declared inside a function are only accessible inside that function.
3. **Function Scope**: Variables declared with `var` are function-scoped, even within blocks.
4. **Block Scope**: Variables declared with `let` and `const` are block-scoped.
5. **Lexical Scope**: Functions have access to variables from their outer scope.
6. **Scope Chain**: Variables are accessed by traversing the scope chain.
7. **Hoisting**: Declarations are hoisted, but not initializations.

---

### 🔗 Resources
- [MDN: Variable Scope](https://developer.mozilla.org/en-US/docs/Glossary/Scope)
- [JavaScript.info: Scope](https://javascript.info/scope-chain-variable-environment)

---

### 🎉 Recap
Understanding variable scope helps you manage where and when you can access variables in your JavaScript programs. It’s crucial to know about **global, local, function, block scope**, and how **hoisting** affects your code. With this knowledge, you can avoid bugs related to variable accessibility and improve code readability.

