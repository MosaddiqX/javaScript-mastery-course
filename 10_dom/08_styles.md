# 🎨 Managing Inline Styles in JavaScript

In JavaScript, manipulating the inline styles of DOM elements is essential for dynamic web applications. You can directly modify an element's style properties through the `style` property, which gives you access to its CSS styles.

---

## 🛠️ Working with Inline Styles

The `style` property allows you to modify an element's inline CSS styles. These styles override any styles set by external or internal stylesheets.

---

### 1. **Accessing Inline Styles**

To access the inline styles of an element, you can use the `style` property. The `style` object only contains the inline styles (i.e., styles set directly in the `style` attribute of the element).

```javascript
const element = document.getElementById("elementId");
console.log(element.style.backgroundColor);  // Logs the background color (if set inline)
```

- **Example:**

```html
<div id="box" style="width: 100px; height: 100px; background-color: red;">
  This is a box.
</div>

<script>
  const box = document.getElementById("box");
  console.log(box.style.backgroundColor);  // Logs: red
</script>
```

In this case, we access the inline `backgroundColor` of the element.

---

### 2. **Modifying Inline Styles**

You can modify the inline styles of an element by directly setting properties on the `style` object. These changes will be reflected immediately on the page.

```javascript
const element = document.getElementById("elementId");
element.style.backgroundColor = "blue";  // Changes background color to blue
element.style.width = "200px";           // Changes width to 200px
```

- **Example:**

```html
<div id="box" style="width: 100px; height: 100px; background-color: red;">
  This is a box.
</div>

<script>
  const box = document.getElementById("box");
  box.style.backgroundColor = "blue";  // Changes the background color to blue
  box.style.height = "150px";           // Changes the height to 150px
</script>
```

After the script runs, the box will be blue with a height of 150px.

---

### 3. **Modifying Multiple Styles at Once**

While you can modify individual style properties, you can also apply multiple styles at once by setting them directly on the `style` object.

```javascript
const element = document.getElementById("elementId");
element.style.cssText = "background-color: green; width: 300px; height: 200px;";
```

- **Example:**

```html
<div id="box" style="width: 100px; height: 100px; background-color: red;">
  This is a box.
</div>

<script>
  const box = document.getElementById("box");
  box.style.cssText = "background-color: green; width: 300px; height: 200px;";  // Sets multiple styles
</script>
```

This example updates the box's background color, width, and height all at once.

---

### 4. **Working with Shorthand Properties**

Some CSS properties can be set using shorthand, such as `border`, `margin`, and `padding`. Here's how you can use them:

```javascript
element.style.border = "2px solid black";  // Sets border to 2px solid black
element.style.margin = "20px";              // Sets margin to 20px
```

- **Example:**

```html
<div id="box" style="width: 100px; height: 100px; background-color: red;">
  This is a box.
</div>

<script>
  const box = document.getElementById("box");
  box.style.border = "5px dashed blue";  // Adds a dashed blue border
  box.style.margin = "10px";              // Adds a margin of 10px
</script>
```

---

### 5. **Using `getComputedStyle()` for Non-inline Styles**

To retrieve styles that are applied via external or internal stylesheets (not inline styles), you can use `getComputedStyle()`:

```javascript
const element = document.getElementById("elementId");
const styles = getComputedStyle(element);
console.log(styles.backgroundColor);  // Logs the background color (from external styles)
```

- **Example:**

```html
<head>
  <style>
    #box {
      background-color: yellow;
      width: 200px;
    }
  </style>
</head>
<body>
  <div id="box">This is a box</div>
  
  <script>
    const box = document.getElementById("box");
    const styles = getComputedStyle(box);
    console.log(styles.backgroundColor);  // Logs: yellow (from CSS file)
  </script>
</body>
```

In this case, `getComputedStyle()` returns the background color set by the stylesheet, not the inline styles.

---

## ⚡ Key Points to Remember

- The `style` property allows direct access to an element's inline styles.
- Use `style.property` to modify individual properties or `style.cssText` to modify multiple properties at once.
- The `getComputedStyle()` method helps retrieve computed styles (e.g., styles applied through CSS) on an element.

---

## 📚 Resources

- [MDN - CSSStyleDeclaration](https://developer.mozilla.org/en-US/docs/Web/API/CSSStyleDeclaration)
- [MDN - getComputedStyle](https://developer.mozilla.org/en-US/docs/Web/API/Window/getComputedStyle)
