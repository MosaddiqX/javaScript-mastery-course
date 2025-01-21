# 💡 `Map` Data Structure in JavaScript

The `Map` is a built-in object in JavaScript that holds key-value pairs. Unlike regular objects, the keys in a `Map` can be of any data type (objects, arrays, primitives, etc.), and they maintain the order of insertion.

---

## 🔥 Syntax of `Map`

```javascript
let map = new Map();
```

- You create a `Map` object using the `new Map()` constructor.
- A `Map` holds **key-value** pairs, where each key is unique.

---

## 🚀 Creating a Map

### Basic Example

```javascript
const map = new Map();

map.set('name', 'John');
map.set('age', 30);

console.log(map);  // Output: Map { 'name' => 'John', 'age' => 30 }
```

In this example, we create a `Map` and use the `set()` method to add key-value pairs.

---

## 🧩 Key Operations on a Map

### 1. **`set()`**: Adding/Updating Values

```javascript
map.set(key, value);
```

- Adds a new key-value pair to the map or updates the value if the key already exists.

---

### 2. **`get()`**: Accessing Values

```javascript
let value = map.get(key);
```

- Retrieves the value associated with the provided key. Returns `undefined` if the key doesn't exist.

---

### 3. **`has()`**: Checking for Existence

```javascript
let exists = map.has(key);
```

- Returns `true` if the key exists in the map, `false` otherwise.

---

### 4. **`delete()`**: Removing a Key-Value Pair

```javascript
map.delete(key);
```

- Removes the key-value pair from the map based on the key. Returns `true` if successful, `false` if the key wasn't found.

---

### 5. **`clear()`**: Removing All Entries

```javascript
map.clear();
```

- Removes all key-value pairs from the map.

---

### 6. **`size`**: Getting the Map's Size

```javascript
let size = map.size;
```

- Returns the number of key-value pairs in the map.

---

## 🚀 Example of Using `Map`

```javascript
const map = new Map();

// Adding data
map.set('name', 'Alice');
map.set('job', 'Developer');
map.set('age', 25);

// Accessing data
console.log(map.get('name'));  // Output: 'Alice'

// Checking if key exists
console.log(map.has('job'));  // Output: true

// Deleting a key-value pair
map.delete('age');
console.log(map.size);  // Output: 2 (after deletion)

map.clear();  // Clears all key-value pairs
console.log(map.size);  // Output: 0
```

In this example, we create a `Map`, add, access, and delete key-value pairs, and check the map's size.

---

## 🚀 Advantages of `Map`

1. **Flexible Keys**: Keys in a `Map` can be any data type (objects, arrays, primitives).
2. **Preserved Insertion Order**: Maps remember the order of the keys as they are inserted, unlike regular JavaScript objects, which don't guarantee order.
3. **Built-in Methods**: `Map` provides a rich set of methods such as `set()`, `get()`, `has()`, `delete()`, `clear()`, and `size` to work with key-value pairs effectively.
4. **Iteration Support**: You can directly iterate over the entries in a `Map` using methods like `forEach()`, or through loops.

---

### 🧩 Example: Iterating Over a Map

```javascript
const map = new Map([
  ['name', 'Bob'],
  ['job', 'Designer'],
  ['age', 28]
]);

// Iterating using forEach()
map.forEach((value, key) => {
  console.log(`${key}: ${value}`);
});
```

Output:
```
name: Bob
job: Designer
age: 28
```

In this example, we use `forEach()` to iterate over the map and log each key-value pair.

---

## 🚀 Key Takeaways

1. **Order Preservation**: Unlike objects, `Map` preserves the order of the keys.
2. **Flexible Keys**: Keys can be any data type, not just strings or symbols.
3. **Performance**: Maps provide better performance for frequently adding/removing key-value pairs compared to objects.
4. **Useful Methods**: `Map` provides various built-in methods like `set()`, `get()`, `has()`, `delete()`, and `clear()` to interact with key-value pairs.

---

## 🔗 Resources

- [MDN: Map](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Map)
- [JavaScript Map Documentation](https://www.javascript.info/map)

---

### 🎉 Recap

- **Key-Value Structure**: Maps store key-value pairs, where keys can be any data type, unlike regular objects.
- **Rich API**: Maps have a rich set of methods that make it easy to interact with the data, ensuring better control and flexibility compared to objects.

