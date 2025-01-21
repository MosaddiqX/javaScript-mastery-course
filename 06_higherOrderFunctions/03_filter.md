# 🔍 `filter()` Method in JavaScript

The `filter()` method is an **array method** in JavaScript that creates a new array with all elements that pass the test implemented by the provided function. It's perfect for extracting elements that satisfy specific conditions.

---

## 🔥 Syntax of `filter()`

The syntax of the `filter()` method is:

```javascript
let newArray = array.filter((currentValue, index, array) => {
  // Return true or false for each element
});
```

- **currentValue**: The current element being processed in the array.
- **index** (optional): The index of the current element.
- **array** (optional): The array that the `filter()` method is called on.

The `filter()` method returns a new array containing all elements for which the provided callback function returns `true`.

---

## 🚀 Example of `filter()`

### Basic Example

```javascript
const numbers = [1, 2, 3, 4, 5, 6];
const evenNumbers = numbers.filter(num => num % 2 === 0);

console.log(evenNumbers);  // Output: [2, 4, 6]
```

In this example, `filter()` is used to select only the even numbers from the `numbers` array, creating a new array with the values `[2, 4, 6]`.

---

## 🧩 Using Index in `filter()`

You can also access the index of the current element inside the callback function.

### Example: Accessing Index

```javascript
const ages = [18, 25, 15, 30, 17];
const adults = ages.filter((age, index) => {
  return age >= 18;
});

console.log(adults);  
// Output: [18, 25, 30]
```

Here, the `filter()` method checks if the `age` is greater than or equal to 18 and returns a new array containing only the adult ages.

---

## 🚀 `filter()` for Complex Conditions

You can apply more complex filtering conditions inside the `filter()` method.

### Example: Filtering Strings with Multiple Conditions

```javascript
const words = ['apple', 'banana', 'kiwi', 'orange', 'mango'];
const longWords = words.filter(word => word.length > 5);

console.log(longWords);  
// Output: ['banana', 'orange']
```

In this case, `filter()` selects words that have more than 5 characters, creating a new array with the words `'banana'` and `'orange'`.

---

## 🧩 Combining `filter()` with Other Methods

The `filter()` method can be combined with other array methods like `map()`, `reduce()`, or `forEach()` for more powerful transformations.

### Example: Combining with `map()`

```javascript
const numbers = [1, 2, 3, 4, 5, 6];
const evenSquares = numbers
  .filter(num => num % 2 === 0)  // Filter even numbers
  .map(num => num ** 2);  // Square them

console.log(evenSquares);  
// Output: [4, 16, 36]
```

Here, `filter()` is used first to select even numbers, and then `map()` is used to square those numbers, resulting in a new array `[4, 16, 36]`.

---

## 🚀 Key Takeaways

1. **Data Filtering**: `filter()` is ideal for extracting specific elements from an array based on conditions.
2. **Returns a New Array**: Unlike `forEach()`, `filter()` returns a new array, leaving the original array unchanged.
3. **Works with Complex Conditions**: You can filter data based on multiple conditions or even combine it with other methods for more powerful operations.

---

## 🔗 Resources
- [MDN: Array.prototype.filter](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/filter)
- [JavaScript.info: Array Methods](https://javascript.info/array-methods)

---

### 🎉 Recap

The `filter()` method allows you to select elements from an array that satisfy a certain condition. It returns a new array with the elements that meet the condition, making it a great tool for filtering and extracting data.
