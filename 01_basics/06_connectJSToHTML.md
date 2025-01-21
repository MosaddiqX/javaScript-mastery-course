# 🔗 Connecting JavaScript with HTML

To make your web pages dynamic and interactive, you need to link JavaScript to HTML. Here's how to do it effectively.

---

## 🛠️ Methods to Connect JavaScript with HTML

### 1. **Inline JavaScript**
- Write JavaScript code directly inside HTML tags using the `onclick`, `onmouseover`, etc., attributes.
- **Example**:
```html
<button onclick="alert('Button clicked!')">Click Me</button>
```

### 🔴 Drawbacks:
- Inline JavaScript makes code messy and hard to maintain.
- Not recommended for professional development.

---

### 2. **Internal JavaScript**
- Place JavaScript code inside `<script>` tags within the same HTML file.
- **Example**:
```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Internal JS</title>
</head>
<body>
  <h1 id="title">Hello, World!</h1>
  <script>
    document.getElementById("title").textContent = "Welcome to JavaScript!";
  </script>
</body>
</html>
```

### ⚠️ Note:
- The `<script>` tag should ideally be placed before the closing `</body>` tag to prevent blocking the page load.

---

### 3. **External JavaScript**
- Write JavaScript code in a separate `.js` file and link it to the HTML file.
- **Example**:

#### `index.html`:
```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>External JS</title>
</head>
<body>
  <h1 id="title">Hello, World!</h1>
  <script src="script.js"></script>
</body>
</html>
```

#### `script.js`:
```javascript
document.getElementById("title").textContent = "Welcome to External JavaScript!";
```

### ✅ Benefits:
- Keeps HTML and JavaScript code separate.
- Improves readability and reusability.

---

## 🕵️‍♂️ Best Practices for Linking JavaScript

### 1. **Defer Attribute**
- Ensures the script is executed after the HTML is fully parsed.
- Example:
```html
<script src="script.js" defer></script>
```

### 2. **Async Attribute**
- Downloads the script asynchronously without blocking HTML parsing.
- Executes as soon as the script is loaded.
- Example:
```html
<script src="script.js" async></script>
```

### ⚠️ When to Use:
- **Defer**: For scripts that manipulate the DOM.  
- **Async**: For scripts that do not depend on the DOM or other scripts.

---

## 🔥 JavaScript in the `<head>` vs `<body>`

### 1. **In the `<head>`:**
- JavaScript is executed **before** the HTML is fully loaded.
- May cause **render-blocking**.

```html
<head>
  <script src="script.js"></script>
</head>
```

### 2. **In the `<body>`:**
- JavaScript runs **after** the HTML is loaded.
- Ensures the DOM is fully available for manipulation.

```html
<body>
  <script src="script.js"></script>
</body>
```

### 🏆 Best Practice:
- Place `<script>` tags at the end of the `<body>` or use the `defer` attribute in the `<head>`.

---

## 🧪 Example: Connecting JS to HTML

### File Structure:
```
project/
│
├── index.html
├── script.js
```

### `index.html`:
```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>JavaScript Example</title>
</head>
<body>
  <h1 id="title">Original Title</h1>
  <button id="changeText">Change Text</button>
  <script src="script.js"></script>
</body>
</html>
```

### `script.js`:
```javascript
const button = document.getElementById("changeText");
const title = document.getElementById("title");

button.addEventListener("click", () => {
  title.textContent = "Text Changed!";
});
```

### Output:
- Clicking the button changes the text of the heading.

---

## 💡 Key Takeaways
1. Use **external JavaScript** for clean and maintainable code.  
2. Place `<script>` tags at the end of `<body>` or use the `defer` attribute.  
3. Avoid inline JavaScript to keep your code modular.  
4. Test your scripts in different browsers to ensure compatibility.

---

### 🔗 Resources
- [MDN: Script Element](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/script)  
- [JavaScript.info: Linking Scripts](https://javascript.info/script-async-defer)  

---

### 🎉 Recap
Connecting JavaScript with HTML is the first step to building interactive web pages. Master the basics, and you'll be ready to create dynamic, engaging experiences!
