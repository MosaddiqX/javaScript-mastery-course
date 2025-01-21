# 🔄 Type Conversion in JavaScript

Type conversion refers to the process of converting one data type to another. JavaScript automatically performs **type coercion** in many cases, but it also allows you to explicitly convert values between different types.

---

## 🔥 Implicit Type Conversion (Type Coercion)

JavaScript **automatically** converts one type to another when necessary. This process is called **type coercion**.

### 1. **String Concatenation**

When a number is concatenated with a string, JavaScript converts the number to a string.

```javascript
let result = 5 + "5";  // "55"
console.log(result);
```

### 2. **Addition with Numbers**

When you use the `+` operator between two numbers, JavaScript adds them together. However, when mixed with a string, it performs **concatenation** instead of addition.

```javascript
let result = 5 + 5;  // 10
console.log(result);
```

---

## 🚀 Explicit Type Conversion

You can explicitly convert one type to another using JavaScript functions.

### 1. **Converting to a String**

#### Using `String()`

```javascript
let num = 10;
let str = String(num);  // "10"
console.log(str);
```

#### Using `toString()`

```javascript
let num = 10;
let str = num.toString();  // "10"
console.log(str);
```

### 2. **Converting to a Number**

#### Using `Number()`

```javascript
let str = "10";
let num = Number(str);  // 10
console.log(num);
```

#### Using `parseInt()` (for integers)

```javascript
let str = "10.5";
let num = parseInt(str);  // 10
console.log(num);
```

#### Using `parseFloat()` (for floating-point numbers)

```javascript
let str = "10.5";
let num = parseFloat(str);  // 10.5
console.log(num);
```

### 3. **Converting to a Boolean**

#### Using `Boolean()`

Any value can be converted to a Boolean using the `Boolean()` function. 

- **Falsy values:** `undefined`, `null`, `0`, `NaN`, `""` (empty string)
- **Truthy values:** All other values

```javascript
let truthy = Boolean(1);  // true
let falsy = Boolean(0);   // false
console.log(truthy, falsy);
```

---

## 🧑‍💻 Example: Type Conversion in Action

### `script.js`
```javascript
let str = "123";
let num = 10;

console.log(Number(str));         // 123
console.log(parseInt(str));       // 123
console.log(Boolean("Hello"));    // true
console.log(Boolean(0));          // false
```

### Output:
```
123
123
true
false
```

---

## 🧩 Type Coercion in Comparison

In JavaScript, type coercion occurs in comparison operations as well.

### 1. **Loose Equality (`==`)**
- The `==` operator converts values to the same type before comparing them.

```javascript
console.log(5 == "5");  // true
console.log(null == undefined);  // true
```

### 2. **Strict Equality (`===`)**
- The `===` operator **does not** perform type coercion. It checks both value and type.

```javascript
console.log(5 === "5");  // false
console.log(null === undefined);  // false
```

---

## 💡 Key Takeaways
1. **Implicit Type Conversion**: JavaScript automatically converts between types in certain situations (e.g., string + number).
2. **Explicit Type Conversion**: Use **`String()`**, **`Number()`**, **`Boolean()`**, etc., to explicitly convert values.
3. **Falsy and Truthy Values**: Understand that some values (e.g., `0`, `false`, `""`) are considered **falsy**, while others are **truthy**.
4. **Strict Equality**: Always prefer using `===` to avoid unexpected behavior due to type coercion.

---

### 🔗 Resources
- [MDN: Type Conversion](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number)
- [JavaScript.info: Type Conversion](https://javascript.info/type-conversions)

---

### 🎉 Recap
Type conversion is a crucial concept in JavaScript. While implicit type conversion can be handy, it’s best to use explicit conversions to ensure the accuracy of your code. Always keep in mind the behavior of **truthy** and **falsy** values.
