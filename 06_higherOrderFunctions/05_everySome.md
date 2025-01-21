# 💡 `every()` and `some()` Methods in JavaScript

The `every()` and `some()` methods are array methods in JavaScript that help you test whether all or some elements in an array pass a given test. These methods return a **boolean value** based on the condition provided.

---

## 🔥 `every()` Method

The `every()` method checks if **all** elements in an array satisfy the condition implemented in the callback function. If **every** element passes the test, it returns `true`, otherwise, it returns `false`.

### Syntax of `every()`

```javascript
let result = array.every((currentValue, index, array) => {
  // Return true or false for each element
});
```

- **currentValue**: The current element being processed in the array.
- **index** (optional): The index of the current element.
- **array** (optional): The array that `every()` is called on.

---

### 🚀 Example of `every()`

```javascript
const numbers = [2, 4, 6, 8];
const allEven = numbers.every(num => num % 2 === 0);

console.log(allEven);  // Output: true
```

In this example, `every()` checks if every number in the array is even. Since all elements satisfy the condition, the result is `true`.

---

### 🧩 Example Where `every()` Returns `false`

```javascript
const numbers = [2, 4, 6, 7];
const allEven = numbers.every(num => num % 2 === 0);

console.log(allEven);  // Output: false
```

Here, the array contains `7`, which is not even. Therefore, `every()` returns `false`.

---

## 🔥 `some()` Method

The `some()` method checks if **at least one** element in the array satisfies the condition provided in the callback function. If **any** element passes the test, it returns `true`, otherwise, it returns `false`.

### Syntax of `some()`

```javascript
let result = array.some((currentValue, index, array) => {
  // Return true or false for each element
});
```

- **currentValue**: The current element being processed in the array.
- **index** (optional): The index of the current element.
- **array** (optional): The array that `some()` is called on.

---

### 🚀 Example of `some()`

```javascript
const numbers = [2, 4, 6, 8];
const someEven = numbers.some(num => num % 2 === 0);

console.log(someEven);  // Output: true
```

In this case, `some()` checks if any number in the array is even. Since all elements are even, the result is `true`.

---

### 🧩 Example Where `some()` Returns `true`

```javascript
const numbers = [2, 4, 6, 7];
const someEven = numbers.some(num => num % 2 === 0);

console.log(someEven);  // Output: true
```

Even though the array contains an odd number (`7`), `some()` returns `true` because there are even numbers (`2`, `4`, `6`).

---

### 🧩 Example Where `some()` Returns `false`

```javascript
const numbers = [1, 3, 5, 7];
const someEven = numbers.some(num => num % 2 === 0);

console.log(someEven);  // Output: false
```

In this case, there are no even numbers in the array, so `some()` returns `false`.

---

## 🚀 Key Takeaways

1. **`every()`**: Checks if **every element** in the array satisfies the provided condition. Returns `true` if all elements meet the criteria, and `false` if at least one does not.
2. **`some()`**: Checks if **any element** in the array satisfies the condition. Returns `true` if at least one element meets the criteria, and `false` if none do.
3. **Boolean Return**: Both methods return a **boolean** value (`true` or `false`), which can be useful for validation and conditions.
4. **Performance**: The `every()` method stops iterating through the array as soon as it finds an element that doesn't meet the condition. Similarly, `some()` stops when it finds an element that satisfies the condition.

---

## 🔗 Resources
- [MDN: Array.prototype.every](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/every)
- [MDN: Array.prototype.some](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/some)

---

### 🎉 Recap

- **`every()`**: Use it when you need to check if **all** elements in an array meet a condition.
- **`some()`**: Use it when you need to check if **at least one** element meets a condition.

