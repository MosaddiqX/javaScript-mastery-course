# 🗂️ Arrays in JavaScript

Arrays are used to store multiple values in a single variable. They are essential for working with collections of data, such as lists or sequences.

---

## 🔥 Creating Arrays

Arrays in JavaScript can be created using **square brackets** `[]`, with values separated by commas.

### Syntax:
```javascript
let arrayName = [value1, value2, value3];
```

### Example: Creating an Array

```javascript
let fruits = ["apple", "banana", "cherry"];
console.log(fruits);
```

### Output:
```
["apple", "banana", "cherry"]
```

---

## 🚀 Accessing Array Elements

You can access elements in an array using the **index** (starting from 0) inside square brackets.

### Syntax:
```javascript
arrayName[index];
```

### Example: Accessing Elements

```javascript
let fruits = ["apple", "banana", "cherry"];
console.log(fruits[1]);  // "banana"
```

### Output:
```
banana
```

---

## 🧩 Modifying Array Elements

You can modify an array element by assigning a new value to a specific index.

### Example: Modifying an Array Element

```javascript
let fruits = ["apple", "banana", "cherry"];
fruits[1] = "orange";  // Changing "banana" to "orange"
console.log(fruits);
```

### Output:
```
["apple", "orange", "cherry"]
```

---

## 🚀 Array Methods

JavaScript arrays come with a variety of built-in methods to manipulate the array. Below are some of the most commonly used methods:

### 1. **`push()`** - Add to the End

Adds one or more elements to the end of an array.

```javascript
let fruits = ["apple", "banana"];
fruits.push("cherry");  // Adds "cherry" to the end
console.log(fruits);
```

### Output:
```
["apple", "banana", "cherry"]
```

---

### 2. **`pop()`** - Remove from the End

Removes the last element from an array.

```javascript
let fruits = ["apple", "banana", "cherry"];
fruits.pop();  // Removes "cherry"
console.log(fruits);
```

### Output:
```
["apple", "banana"]
```

---

### 3. **`shift()`** - Remove from the Beginning

Removes the first element from an array.

```javascript
let fruits = ["apple", "banana", "cherry"];
fruits.shift();  // Removes "apple"
console.log(fruits);
```

### Output:
```
["banana", "cherry"]
```

---

### 4. **`unshift()`** - Add to the Beginning

Adds one or more elements to the beginning of an array.

```javascript
let fruits = ["banana", "cherry"];
fruits.unshift("apple");  // Adds "apple" to the beginning
console.log(fruits);
```

### Output:
```
["apple", "banana", "cherry"]
```

---

### 5. **`slice()`** - Create a Subarray

The `slice()` method returns a shallow copy of a portion of an array.

```javascript
let fruits = ["apple", "banana", "cherry"];
let slicedFruits = fruits.slice(1, 3);  // Gets a subarray from index 1 to 3
console.log(slicedFruits);
```

### Output:
```
["banana", "cherry"]
```

---

## 🧑‍💻 Example: Looping Through an Array

### `script.js`
```javascript
let fruits = ["apple", "banana", "cherry"];
for (let i = 0; i < fruits.length; i++) {
  console.log(fruits[i]);
}
```

### Output:
```
apple
banana
cherry
```

---

## 💡 Key Takeaways
1. **Array Creation**: Arrays are created using square brackets `[]`.
2. **Array Indexing**: Access elements using the index (starting from 0).
3. **Array Modification**: Modify array elements directly via their index.
4. **Array Methods**: Methods like `push()`, `pop()`, `shift()`, and `unshift()` manipulate arrays.
5. **`slice()`**: Creates a subarray from an existing array.

---

### 🔗 Resources
- [MDN: Array](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array)
- [JavaScript.info: Arrays](https://javascript.info/array)

---

### 🎉 Recap
Arrays are powerful data structures that allow you to store multiple values in a single variable. You can access, modify, and manipulate arrays using various built-in methods like `push()`, `pop()`, `shift()`, `unshift()`, and `slice()`.

