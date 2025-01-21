# 🔁 Loops in JavaScript

Loops allow you to repeat a block of code multiple times. They are essential for working with large datasets, performing repetitive tasks, and iterating over collections.

---

## 🔥 `for` Loop

The `for` loop is the most commonly used loop in JavaScript. It includes an initialization, a condition, and an increment/decrement.

### Syntax:
```javascript
for (initialization; condition; increment/decrement) {
  // Code to be executed
}
```

### Example: Looping from 1 to 5

```javascript
for (let i = 1; i <= 5; i++) {
  console.log(i);
}
```

### Output:
```
1
2
3
4
5
```

---

## 🚀 `while` Loop

The `while` loop executes a block of code as long as the condition is true. It checks the condition before each iteration.

### Syntax:
```javascript
while (condition) {
  // Code to be executed
}
```

### Example: Looping while the number is less than 5

```javascript
let i = 1;
while (i <= 5) {
  console.log(i);
  i++;
}
```

### Output:
```
1
2
3
4
5
```

---

## 🧩 `do...while` Loop

The `do...while` loop is similar to the `while` loop, except that it checks the condition after the block of code is executed. This guarantees that the code will run at least once.

### Syntax:
```javascript
do {
  // Code to be executed
} while (condition);
```

### Example: Looping at least once

```javascript
let i = 1;
do {
  console.log(i);
  i++;
} while (i <= 5);
```

### Output:
```
1
2
3
4
5
```

---

## 🚀 Loop Control Statements

You can control the flow of loops using **`break`** and **`continue`** statements.

### 1. **`break` Statement**

The `break` statement is used to exit the loop, regardless of whether the condition is still true.

```javascript
for (let i = 1; i <= 5; i++) {
  if (i === 3) {
    break;  // Exit the loop when i equals 3
  }
  console.log(i);
}
```

### Output:
```
1
2
```

### 2. **`continue` Statement**

The `continue` statement is used to skip the current iteration and proceed to the next one.

```javascript
for (let i = 1; i <= 5; i++) {
  if (i === 3) {
    continue;  // Skip the iteration when i equals 3
  }
  console.log(i);
}
```

### Output:
```
1
2
4
5
```

---

## 🧑‍💻 Example: Looping through an Array

### `script.js`
```javascript
let numbers = [1, 2, 3, 4, 5];
for (let i = 0; i < numbers.length; i++) {
  console.log(numbers[i]);
}
```

### Output:
```
1
2
3
4
5
```

---

## 💡 Key Takeaways
1. **`for` Loop**: Ideal for iterating a known number of times.
2. **`while` Loop**: Continues as long as a condition is true, checks before each iteration.
3. **`do...while` Loop**: Executes at least once, checks after each iteration.
4. **Loop Control**: Use `break` to exit a loop early, and `continue` to skip an iteration.

---

### 🔗 Resources
- [MDN: for loop](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/for)
- [JavaScript.info: Loops](https://javascript.info/while-for)

---

### 🎉 Recap
Loops are essential for performing repetitive tasks. The `for`, `while`, and `do...while` loops allow you to iterate over a block of code multiple times. Understanding when to use each type of loop is crucial for writing efficient and readable code.

