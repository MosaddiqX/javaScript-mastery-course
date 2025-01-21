# 🛠️ `Set` Data Structure in JavaScript

The `Set` is a built-in object in JavaScript that allows you to store unique values of any type, whether primitive values or object references. A `Set` automatically removes duplicate entries and maintains insertion order.

---

## 🔥 Syntax of `Set`

```javascript
let set = new Set();
```

- You create a `Set` object using the `new Set()` constructor.
- A `Set` holds **unique** values, meaning there are no duplicates in a Set.

---

## 🚀 Creating a Set

### Basic Example

```javascript
const set = new Set();

set.add(1);
set.add(2);
set.add(3);

console.log(set);  // Output: Set { 1, 2, 3 }
```

In this example, we create a `Set` and use the `add()` method to add elements. Duplicates are automatically handled.

---

## 🧩 Key Operations on a Set

### 1. **`add()`**: Adding Elements

```javascript
set.add(value);
```

- Adds a new value to the set. If the value already exists, it will not be added again (duplicates are ignored).

---

### 2. **`has()`**: Checking for Existence

```javascript
let exists = set.has(value);
```

- Returns `true` if the value exists in the set, `false` otherwise.

---

### 3. **`delete()`**: Removing an Element

```javascript
set.delete(value);
```

- Removes the specified element from the set. Returns `true` if the element was removed, `false` if it wasn't found.

---

### 4. **`clear()`**: Removing All Elements

```javascript
set.clear();
```

- Removes all elements from the set.

---

### 5. **`size`**: Getting the Set's Size

```javascript
let size = set.size;
```

- Returns the number of unique elements in the set.

---

## 🚀 Example of Using `Set`

```javascript
const set = new Set();

// Adding data
set.add(10);
set.add(20);
set.add(30);
set.add(10);  // Duplicates are ignored

console.log(set);  // Output: Set { 10, 20, 30 }

// Checking for existence
console.log(set.has(20));  // Output: true

// Removing an element
set.delete(30);
console.log(set);  // Output: Set { 10, 20 }

// Clearing all elements
set.clear();
console.log(set.size);  // Output: 0
```

In this example, we create a `Set`, add elements, check for existence, remove an element, and clear all elements.

---

## 🚀 Advantages of `Set`

1. **Unique Values**: A `Set` automatically ensures that all values are unique, so there are no duplicates.
2. **Order Preservation**: A `Set` maintains the insertion order, so the order in which elements are added is preserved.
3. **Efficient Lookups**: Sets provide efficient methods for checking existence (`has()`), adding values, and removing them.
4. **No Key-Value Pairs**: Unlike `Map`, a `Set` only stores values, not key-value pairs.

---

### 🧩 Example: Iterating Over a Set

```javascript
const set = new Set([1, 2, 3, 4, 5]);

// Iterating using forEach()
set.forEach(value => {
  console.log(value);
});
```

Output:
```
1
2
3
4
5
```

In this example, we use `forEach()` to iterate over the values in the set.

---

## 🚀 Key Takeaways

1. **Unique Values**: Sets ensure that all values are unique. If you try to add a duplicate, it will be ignored.
2. **Efficient Lookups**: The `has()` method allows fast lookup of elements in the set.
3. **Iterate and Store**: Sets store values in the order they are added and support iteration through methods like `forEach()`.

---

## 🔗 Resources

- [MDN: Set](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Set)
- [JavaScript Set Documentation](https://www.javascript.info/set)

---

### 🎉 Recap

- **Unique Collection**: A `Set` is a collection of unique values with no duplicates.
- **Efficient Operations**: Provides fast operations for adding, checking, and removing values.

