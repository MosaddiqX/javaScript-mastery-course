# 🏷️ Working with DOM Attributes

Attributes in the DOM define properties of HTML elements, such as their values, IDs, classes, or styles. Manipulating attributes is crucial for dynamic web development.

---

## 🛠️ Working with Attributes in JavaScript

Attributes are not the same as properties. While properties reflect the current state of an element, attributes store the initial state as defined in the HTML markup. You can access and modify these attributes using JavaScript methods.

---

### 1. **Getting an Attribute**

To get the value of an attribute, use the `getAttribute()` method.

```javascript
const element = document.getElementById("myElement");
const value = element.getAttribute("href");
console.log(value);  // Example: 'https://example.com'
```

- **Example:**

```html
<a id="myLink" href="https://example.com">Click here</a>

<script>
    const link = document.getElementById("myLink");
    const hrefValue = link.getAttribute("href");
    console.log(hrefValue);  // 'https://example.com'
</script>
```

This will log the value of the `href` attribute of the link.

---

### 2. **Setting an Attribute**

To set a new value for an attribute, use the `setAttribute()` method.

```javascript
const element = document.getElementById("myElement");
element.setAttribute("src", "newImage.jpg");
```

- **Example:**

```html
<img id="myImage" src="oldImage.jpg" alt="Old Image">

<script>
    const image = document.getElementById("myImage");
    image.setAttribute("src", "newImage.jpg");
</script>
```

This will change the `src` attribute of the image to `newImage.jpg`.

---

### 3. **Removing an Attribute**

To remove an attribute from an element, use the `removeAttribute()` method.

```javascript
const element = document.getElementById("myElement");
element.removeAttribute("disabled");
```

- **Example:**

```html
<button id="myButton" disabled>Click me</button>

<script>
    const button = document.getElementById("myButton");
    button.removeAttribute("disabled");
</script>
```

This will remove the `disabled` attribute, enabling the button.

---

### 4. **Accessing Boolean Attributes**

Boolean attributes like `disabled`, `checked`, or `readonly` can be accessed directly using the element's property. You can also modify these attributes via the `setAttribute()` method.

- **Example:**

```html
<input id="myCheckbox" type="checkbox" checked>

<script>
    const checkbox = document.getElementById("myCheckbox");
    console.log(checkbox.checked);  // true

    checkbox.checked = false;  // Uncheck the checkbox
    console.log(checkbox.checked);  // false
</script>
```

In this case, the `checked` attribute is a boolean attribute. Changing the `checked` property directly reflects the state of the checkbox.

---

### 5. **Working with Data Attributes**

HTML5 introduced `data-*` attributes, which allow you to store extra data on an element without affecting the document's structure. You can access and modify these attributes using the `dataset` property.

```javascript
const element = document.getElementById("myElement");
const dataValue = element.dataset.someData;
console.log(dataValue);  // Example: 'value'
```

- **Example:**

```html
<div id="myElement" data-info="This is some data">Hello</div>

<script>
    const div = document.getElementById("myElement");
    console.log(div.dataset.info);  // 'This is some data'
</script>
```

This logs the value of the `data-info` attribute stored on the element.

---

## ⚡ Key Points About Attributes

- **`getAttribute()`** is used to retrieve an attribute’s value.
- **`setAttribute()`** allows you to modify an attribute's value.
- **`removeAttribute()`** deletes an attribute from the element.
- Boolean attributes (like `checked`, `disabled`) can be accessed directly via the element’s properties.
- `data-*` attributes provide a flexible way to store custom data on HTML elements.

---

## 🧪 Example: Custom Data Attributes

You can use `data-*` attributes to store additional information about an element, and access this data via JavaScript.

```html
<button id="myButton" data-id="123" data-role="admin">Click me</button>

<script>
    const button = document.getElementById("myButton");
    console.log(button.dataset.id);     // '123'
    console.log(button.dataset.role);   // 'admin'
</script>
```

---

## 🎯 Use Cases for Attribute Manipulation

- **Dynamic Forms**: Modify form element attributes (like `disabled`, `readonly`, or `required`) based on user interaction.
- **Interactive UI**: Use custom `data-*` attributes to store and retrieve additional information in a user-friendly manner.
- **Changing Links**: Update link destinations (`href`) dynamically without reloading the page.
- **Image Sources**: Change image sources dynamically based on user input or page content updates.

---

## 📚 Resources

- [MDN - getAttribute](https://developer.mozilla.org/en-US/docs/Web/API/Element/getAttribute)
- [W3Schools - setAttribute](https://www.w3schools.com/jsref/met_element_setattribute.asp)
