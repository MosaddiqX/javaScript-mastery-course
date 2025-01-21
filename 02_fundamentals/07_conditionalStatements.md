# 🧑‍⚖️ Conditional Statements in JavaScript

Conditional statements allow you to perform different actions based on certain conditions. They are fundamental to controlling the flow of your JavaScript programs.

---

## 🔥 `if` Statement

The `if` statement evaluates a condition and executes a block of code if the condition is **true**.

```javascript
let age = 18;

if (age >= 18) {
  console.log("You are an adult.");
}
```

### Output:
```
You are an adult.
```

---

## 🚀 `if...else` Statement

The `if...else` statement allows you to execute one block of code if the condition is **true**, and another if the condition is **false**.

```javascript
let age = 16;

if (age >= 18) {
  console.log("You are an adult.");
} else {
  console.log("You are a minor.");
}
```

### Output:
```
You are a minor.
```

---

## 🧩 `else if` Statement

The `else if` statement allows you to check multiple conditions. It is used when you have more than two conditions to check.

```javascript
let day = "Monday";

if (day === "Saturday" || day === "Sunday") {
  console.log("It's the weekend!");
} else if (day === "Monday") {
  console.log("Start of the workweek!");
} else {
  console.log("It's a weekday.");
}
```

### Output:
```
Start of the workweek!
```

---

## 🚀 Ternary Operator

The ternary operator is a shorthand for the `if...else` statement. It evaluates a condition and returns one value if the condition is true and another if the condition is false.

### Syntax:
```javascript
condition ? expr1 : expr2;
```

```javascript
let age = 20;
let message = age >= 18 ? "You are an adult." : "You are a minor.";
console.log(message);  // "You are an adult."
```

### Output:
```
You are an adult.
```

---

## 🧑‍💻 Example: Using Conditional Statements

### `script.js`
```javascript
let num = 7;

if (num % 2 === 0) {
  console.log("The number is even.");
} else {
  console.log("The number is odd.");
}
```

### Output:
```
The number is odd.
```

---

## 🧩 Nested `if` Statements

You can nest `if` statements inside other `if` statements to evaluate multiple conditions.

```javascript
let num = 10;

if (num > 0) {
  if (num % 2 === 0) {
    console.log("The number is positive and even.");
  } else {
    console.log("The number is positive and odd.");
  }
} else {
  console.log("The number is non-positive.");
}
```

### Output:
```
The number is positive and even.
```

---

## 💡 Key Takeaways
1. **`if` Statement**: Executes code if a condition is true.
2. **`if...else` Statement**: Executes one block of code if a condition is true, and another if it's false.
3. **`else if` Statement**: Check multiple conditions.
4. **Ternary Operator**: Shorthand for `if...else`.
5. **Nested `if` Statements**: You can nest multiple `if` statements to check more complex conditions.

---

### 🔗 Resources
- [MDN: if...else](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/if...else)
- [JavaScript.info: Conditional Operators](https://javascript.info/ifelse)

---

### 🎉 Recap
Conditional statements are essential for making decisions in your code. They let you check conditions and execute different code paths based on whether those conditions are true or false. Mastering these will help you handle various scenarios in your JavaScript programs.

