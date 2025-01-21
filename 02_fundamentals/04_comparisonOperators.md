# 🔍 Comparison Operators in JavaScript

Comparison operators are used to compare two values or expressions. They return a Boolean value (`true` or `false`) based on whether the comparison is true or false.

---

## 🔥 Types of Comparison Operators

### 1. **Equality (`==`)**
- Compares two values for equality, **ignoring** their data type.

```javascript
let result = 5 == '5'; // true
console.log(result);
```

### 2. **Strict Equality (`===`)**
- Compares both the **value** and **type** for equality.
- This is recommended as it avoids type coercion.

```javascript
let result = 5 === '5'; // false
console.log(result);
```

### 3. **Inequality (`!=`)**
- Compares two values for inequality, **ignoring** their type.

```javascript
let result = 5 != '5'; // false
console.log(result);
```

### 4. **Strict Inequality (`!==`)**
- Compares both the **value** and **type** for inequality.

```javascript
let result = 5 !== '5'; // true
console.log(result);
```

---

## 🚀 Relational Comparison Operators

### 1. **Greater than (`>`)**

```javascript
let result = 10 > 5;  // true
console.log(result);
```

### 2. **Less than (`<`)**

```javascript
let result = 5 < 10;  // true
console.log(result);
```

### 3. **Greater than or equal to (`>=`)**

```javascript
let result = 10 >= 10; // true
console.log(result);
```

### 4. **Less than or equal to (`<=`)**

```javascript
let result = 5 <= 10; // true
console.log(result);
```

---

## 🧑‍💻 Combining Comparison Operators

You can combine comparison operators to form more complex conditions.

### 1. **Multiple conditions**
- Use logical operators (`&&`, `||`, `!`) with comparison operators.

```javascript
let age = 25;
let salary = 5000;

// Check if the person is an adult and earns more than $3000
let isEligible = age >= 18 && salary > 3000;
console.log(isEligible); // true
```

### 2. **Using `if-else` with comparison operators**

```javascript
let age = 20;

if (age >= 18) {
  console.log("You are an adult!");
} else {
  console.log("You are a minor.");
}
```

---

## 🧩 Edge Cases to Consider

### 1. **Type Coercion with `==`**
- JavaScript performs type coercion when using the loose equality operator `==`, which can lead to unexpected results.

```javascript
console.log(0 == false);  // true
console.log('0' == false); // true
console.log(null == undefined);  // true
```

To avoid these issues, always use strict equality (`===`) for comparisons.

---

## 🎯 Example: Using Comparison Operators

### `script.js`
```javascript
let num1 = 10;
let num2 = 20;

// Greater than
if (num1 > num2) {
  console.log(`${num1} is greater than ${num2}`);
} else {
  console.log(`${num1} is not greater than ${num2}`);
}

// Strict equality
if (num1 === num2) {
  console.log("Both numbers are equal!");
} else {
  console.log("The numbers are not equal.");
}
```

### Output:
```
10 is not greater than 20
The numbers are not equal.
```

---

## 💡 Key Takeaways
1. **Loose equality (`==`)** allows type coercion, while **strict equality (`===`)** does not.
2. **Comparison operators** help compare numbers, strings, and other data types.
3. Use **logical operators** to combine multiple comparisons and make complex conditions.
4. Always prefer **strict equality** to avoid unexpected results from type coercion.

---

### 🔗 Resources
- [MDN: Comparison Operators](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Comparison_Operators)
- [JavaScript.info: Comparison](https://javascript.info/comparison)

---

### 🎉 Recap
Comparison operators are essential in JavaScript for comparing values and controlling the flow of your program. Always be cautious of type coercion when using the `==` operator, and prefer `===` for accurate comparisons.

