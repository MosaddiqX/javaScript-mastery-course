# ✨ Manipulating Strings in JavaScript

Strings are sequences of characters used to represent text in JavaScript. JavaScript provides a rich set of methods to manipulate strings, making it easier to perform tasks like searching, replacing, and formatting text.

---

## 🔥 Common String Methods

### 1. **`length`**
- The `length` property returns the number of characters in a string.

```javascript
let str = "Hello, World!";
console.log(str.length); // 13
```

### 2. **`charAt()`**
- Returns the character at a specified index.

```javascript
let str = "JavaScript";
console.log(str.charAt(4));  // "S"
```

### 3. **`concat()`**
- Combines multiple strings into one.

```javascript
let str1 = "Hello, ";
let str2 = "World!";
console.log(str1.concat(str2)); // "Hello, World!"
```

---

## 🚀 Modifying Strings

### 1. **`toLowerCase()`**
- Converts all characters in a string to lowercase.

```javascript
let str = "JavaScript";
console.log(str.toLowerCase()); // "javascript"
```

### 2. **`toUpperCase()`**
- Converts all characters in a string to uppercase.

```javascript
let str = "JavaScript";
console.log(str.toUpperCase()); // "JAVASCRIPT"
```

### 3. **`replace()`**
- Replaces a specified substring with another substring.

```javascript
let str = "Hello, World!";
console.log(str.replace("World", "JavaScript")); // "Hello, JavaScript!"
```

### 4. **`slice()`**
- Extracts a portion of a string based on specified start and end indices.

```javascript
let str = "JavaScript";
console.log(str.slice(0, 4)); // "Java"
```

### 5. **`substring()`**
- Similar to `slice()`, but does not accept negative indices.

```javascript
let str = "JavaScript";
console.log(str.substring(0, 4)); // "Java"
```

---

## 🧩 String Search Methods

### 1. **`indexOf()`**
- Returns the index of the first occurrence of a specified substring. Returns `-1` if not found.

```javascript
let str = "JavaScript is fun!";
console.log(str.indexOf("fun"));  // 14
```

### 2. **`includes()`**
- Checks if a specified substring exists in the string. Returns `true` or `false`.

```javascript
let str = "JavaScript is fun!";
console.log(str.includes("fun")); // true
```

### 3. **`startsWith()`**
- Checks if the string starts with a specific substring.

```javascript
let str = "JavaScript is fun!";
console.log(str.startsWith("Java")); // true
```

### 4. **`endsWith()`**
- Checks if the string ends with a specific substring.

```javascript
let str = "JavaScript is fun!";
console.log(str.endsWith("fun!")); // true
```

---

## 🚀 String Formatting

### 1. **Template Literals (```)**
- Template literals allow for easy embedding of expressions and variables within strings.

```javascript
let name = "John";
let age = 30;
let greeting = `Hello, my name is ${name} and I am ${age} years old.`;
console.log(greeting); // "Hello, my name is John and I am 30 years old."
```

### 2. **`padStart()` & `padEnd()`**
- Adds padding to the beginning or end of a string until it reaches the specified length.

```javascript
let str = "5";
console.log(str.padStart(3, "0")); // "005"
console.log(str.padEnd(3, "0"));   // "500"
```

---

## 🧑‍💻 Example: Combining String Methods

### `script.js`
```javascript
let sentence = "I am learning JavaScript!";

// Convert to uppercase
let upperSentence = sentence.toUpperCase();

// Check if the sentence contains 'JavaScript'
let containsJS = sentence.includes("JavaScript");

// Replace 'learning' with 'mastering'
let modifiedSentence = sentence.replace("learning", "mastering");

console.log(upperSentence);         // "I AM LEARNING JAVASCRIPT!"
console.log(containsJS);            // true
console.log(modifiedSentence);     // "I am mastering JavaScript!"
```

### Output:
```
I AM LEARNING JAVASCRIPT!
true
I am mastering JavaScript!
```

---

## 💡 Key Takeaways
1. Use **`length`** to find the number of characters in a string.
2. Modify strings with **`toUpperCase()`**, **`toLowerCase()`**, and **`replace()`**.
3. Extract parts of strings using **`slice()`** and **`substring()`**.
4. Search for substrings with **`indexOf()`**, **`includes()`**, **`startsWith()`**, and **`endsWith()`**.
5. Use **template literals** to format strings with variables and expressions easily.

---

### 🔗 Resources
- [MDN: String](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String)
- [JavaScript.info: Strings](https://javascript.info/string)

---

### 🎉 Recap
String manipulation is one of the most commonly used tasks in JavaScript. By mastering these string methods, you can efficiently search, modify, and format strings for various use cases.

