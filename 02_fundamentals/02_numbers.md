# 🔢 Working with Numbers in JavaScript

In JavaScript, numbers are one of the most common data types. Understanding how to work with them is essential for performing calculations, comparisons, and handling data efficiently.

---

## 🔥 Number Data Type in JavaScript

JavaScript has a single number type for both integers and floating-point values. It follows the IEEE 754 standard for floating-point arithmetic.

### 1. **Integer Numbers**
- Whole numbers, both positive and negative, are integers.
- **Example**:
```javascript
let number = 10;
console.log(number); // 10
```

### 2. **Floating Point Numbers**
- Numbers with decimals are called floating-point numbers.
- **Example**:
```javascript
let price = 19.99;
console.log(price); // 19.99
```

### 3. **NaN (Not a Number)**
- JavaScript can return `NaN` when an operation doesn't yield a valid number.
- **Example**:
```javascript
let invalidResult = "Hello" / 2;
console.log(invalidResult); // NaN
```

---

## 🚀 Useful Number Methods

### 1. **`Number.isNaN()`**
- Checks whether a value is `NaN`.
- **Example**:
```javascript
console.log(Number.isNaN(25)); // false
console.log(Number.isNaN(NaN)); // true
```

### 2. **`parseInt()`**
- Converts a string to an integer.
- **Example**:
```javascript
let number = parseInt("123");
console.log(number); // 123
```

### 3. **`parseFloat()`**
- Converts a string to a floating-point number.
- **Example**:
```javascript
let number = parseFloat("10.25");
console.log(number); // 10.25
```

### 4. **`toFixed()`**
- Rounds a number to a specified number of decimal places and returns it as a string.
- **Example**:
```javascript
let price = 19.9999;
console.log(price.toFixed(2)); // "20.00"
```

---

## 🧮 Arithmetic Operations

JavaScript supports basic arithmetic operations such as addition, subtraction, multiplication, division, and more.

### 1. **Addition (+)**
```javascript
let sum = 10 + 5;
console.log(sum); // 15
```

### 2. **Subtraction (-)**
```javascript
let difference = 10 - 5;
console.log(difference); // 5
```

### 3. **Multiplication (*)**
```javascript
let product = 10 * 5;
console.log(product); // 50
```

### 4. **Division (/)**
```javascript
let quotient = 10 / 5;
console.log(quotient); // 2
```

### 5. **Modulo (%)**
- The remainder of division.
```javascript
let remainder = 10 % 3;
console.log(remainder); // 1
```

---

## 🧑‍💻 Advanced Number Operations

### 1. **Exponentiation (`**`)**
- Raising a number to a power.
```javascript
let power = 2 ** 3; // 2 raised to the power of 3
console.log(power); // 8
```

### 2. **`Math.pow()`**
- An alternative to exponentiation.
```javascript
let power = Math.pow(2, 3); // 2 raised to the power of 3
console.log(power); // 8
```

### 3. **`Math.random()`**
- Generates a random floating-point number between 0 (inclusive) and 1 (exclusive).
```javascript
let randomNumber = Math.random();
console.log(randomNumber); // Random value between 0 and 1
```

### 4. **`Math.round()`**
- Rounds a number to the nearest integer.
```javascript
let rounded = Math.round(19.8);
console.log(rounded); // 20
```

### 5. **`Math.floor()`**
- Rounds a number down to the nearest integer.
```javascript
let floored = Math.floor(19.8);
console.log(floored); // 19
```

### 6. **`Math.ceil()`**
- Rounds a number up to the nearest integer.
```javascript
let ceiled = Math.ceil(19.2);
console.log(ceiled); // 20
```

---

## 🛠️ Working with Large and Small Numbers

### 1. **Infinity and -Infinity**

- **Infinity** represents a number greater than any other number.
- **-Infinity** represents a number smaller than any other number.
- **Example**:
```javascript
let positiveInfinity = Infinity;
let negativeInfinity = -Infinity;

console.log(positiveInfinity); // Infinity
console.log(negativeInfinity); // -Infinity
```

### 2. **`Number.MAX_VALUE` and `Number.MIN_VALUE`**

- **`Number.MAX_VALUE`** is the largest possible number in JavaScript.
- **`Number.MIN_VALUE`** is the smallest positive number.
- **Example**:
```javascript
console.log(Number.MAX_VALUE); // 1.7976931348623157e+308
console.log(Number.MIN_VALUE); // 5e-324
```

---

## 🔢 Number Comparison

### 1. **Comparing Numbers**

- **Equality**: Use `==` or `===` to check if two numbers are equal.
- **Greater than, Less than**: Use `>`, `<`, `>=`, `<=` for comparisons.

```javascript
let a = 5;
let b = 10;
console.log(a > b); // false
console.log(a < b); // true
console.log(a == b); // false
console.log(a === b); // false
```

---

## 🎯 Example: Working with Numbers

### `script.js`
```javascript
// Declaring numbers
let price = 15.75;
let discount = 5;

// Performing arithmetic operations
let finalPrice = price - discount;
console.log(`Final price after discount: $${finalPrice.toFixed(2)}`);

// Generating a random number
let randomDiscount = Math.random() * 10;
console.log(`Random discount: $${randomDiscount.toFixed(2)}`);
```

### Output:
```
Final price after discount: $10.75
Random discount: $4.23
```

---

## 💡 Key Takeaways
1. JavaScript uses **floating-point numbers** for both integers and decimals.
2. Use **`Math` methods** to perform advanced number operations like rounding, generating random numbers, etc.
3. **Understand Infinity and NaN** when dealing with large/small numbers or invalid operations.
4. Use **comparison operators** for number comparisons.

---

### 🔗 Resources
- [MDN: Number](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number)  
- [JavaScript.info: Numbers](https://javascript.info/number)

---

### 🎉 Recap
Working with numbers in JavaScript is straightforward, but knowing the right methods and operations is key to solving more complex problems. Practice using `Math` functions and understanding the limitations of floating-point arithmetic to improve your number handling skills.
