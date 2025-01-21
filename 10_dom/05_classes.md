# 🧑‍🎤 Managing CSS Classes in the DOM

In JavaScript, manipulating CSS classes of DOM elements is a common task. The `classList` property provides an easy way to add, remove, or toggle classes dynamically without affecting other classes on the element.

---

## 🏷️ Working with `classList`

The `classList` property returns a live `DOMTokenList` collection of the element's class attributes. It offers methods like `add()`, `remove()`, `toggle()`, and `contains()` to manipulate the classes.

---

### 1. **Adding a Class**

You can add a class to an element using the `classList.add()` method.

```javascript
const element = document.getElementById("myElement");
element.classList.add("new-class");
```

- **Example:**

```html
<p id="message">Hello World</p>

<script>
    const message = document.getElementById("message");
    message.classList.add("highlight");
</script>
```

This will add the `highlight` class to the `<p>` element, which can be styled using CSS.

---

### 2. **Removing a Class**

To remove a class from an element, you can use the `classList.remove()` method.

```javascript
const element = document.getElementById("myElement");
element.classList.remove("old-class");
```

- **Example:**

```html
<p id="message" class="highlight">Hello World</p>

<script>
    const message = document.getElementById("message");
    message.classList.remove("highlight");
</script>
```

This will remove the `highlight` class from the `<p>` element.

---

### 3. **Toggling a Class**

The `classList.toggle()` method is used to toggle a class on and off. If the class exists, it will be removed; if it doesn't exist, it will be added.

```javascript
const element = document.getElementById("myElement");
element.classList.toggle("active");
```

- **Example:**

```html
<button id="toggleButton">Toggle Class</button>
<p id="message">Hello World</p>

<script>
    const button = document.getElementById("toggleButton");
    const message = document.getElementById("message");

    button.addEventListener("click", () => {
        message.classList.toggle("highlight");
    });
</script>
```

Here, clicking the button will toggle the `highlight` class on the `<p>` element.

---

### 4. **Checking for a Class**

To check if an element has a specific class, you can use the `classList.contains()` method, which returns `true` if the class exists, otherwise `false`.

```javascript
const element = document.getElementById("myElement");
if (element.classList.contains("highlight")) {
    console.log("The element has the highlight class.");
}
```

- **Example:**

```html
<p id="message" class="highlight">Hello World</p>

<script>
    const message = document.getElementById("message");
    if (message.classList.contains("highlight")) {
        console.log("The element has the highlight class.");
    }
</script>
```

---

## ⚡ Key Points about `classList`

- `classList` provides a simpler and more efficient way to manipulate CSS classes than directly modifying the `className` property.
- It doesn’t overwrite other classes, only modifies the specific class you target.
- `classList` methods do not affect inline styles of the element.

---

## 🧪 Example: Toggle Dark Mode Class

You can use `classList.toggle()` to implement features like dark mode toggling:

```html
<button id="darkModeButton">Toggle Dark Mode</button>

<script>
    const button = document.getElementById("darkModeButton");
    button.addEventListener("click", () => {
        document.body.classList.toggle("dark-mode");
    });
</script>
```

This toggles the `dark-mode` class on the `body` element, allowing you to apply different CSS styles for dark mode.

---

## 🎯 Use Cases for `classList`

- **Dynamic Theme Changes**: Toggle dark/light mode on your site.
- **Interactive UI**: Dynamically apply or remove classes to show or hide elements, change layout, or animate elements.
- **Element Highlighting**: Add/remove classes to emphasize specific elements in response to user interactions.

---

## 📚 Resources

- [MDN - classList](https://developer.mozilla.org/en-US/docs/Web/API/Element/classList)
- [W3Schools - classList](https://www.w3schools.com/jsref/prop_element_classlist.asp)
