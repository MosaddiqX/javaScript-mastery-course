# 🖱️ DOM Events & Event Handling

In JavaScript, DOM events allow you to interact with the HTML elements and trigger actions based on user input or other events. Event handling is crucial for building interactive web pages, such as form submissions, button clicks, mouse movements, and more.

---

## 🛠️ Types of DOM Events

Some common DOM events include:

- **Click events**: Triggered when an element is clicked.
- **Mouse events**: `mouseover`, `mouseout`, `mousemove`, etc.
- **Keyboard events**: `keydown`, `keyup`, `keypress`.
- **Input events**: `change`, `input`, `focus`, `blur`.
- **Load events**: Triggered when the page or an image is fully loaded.
- **Form events**: `submit`, `reset`.

---

## 🧑‍💻 Adding Event Listeners

To handle events, you can use the `addEventListener()` method, which attaches an event handler to a specified element.

### Syntax

```javascript
element.addEventListener(event, function, useCapture);
```

- `event`: The type of event to listen for (e.g., `click`, `mouseover`).
- `function`: The function to run when the event occurs.
- `useCapture`: Optional. A Boolean value that indicates whether the event should be captured during the capturing phase (`true`) or the bubbling phase (`false`).

---

### Example: Adding a Click Event

```html
<button id="myButton">Click Me!</button>

<script>
  const button = document.getElementById('myButton');
  
  button.addEventListener('click', function() {
    alert('Button clicked!');
  });
</script>
```

In this example, clicking the "Click Me!" button will trigger the event listener and show an alert.

---

### Example: Mouseover Event

```html
<div id="myDiv" style="width: 100px; height: 100px; background-color: lightblue;">
  Hover over me!
</div>

<script>
  const div = document.getElementById('myDiv');
  
  div.addEventListener('mouseover', function() {
    div.style.backgroundColor = 'lightgreen'; // Changes the background color on hover
  });
  
  div.addEventListener('mouseout', function() {
    div.style.backgroundColor = 'lightblue'; // Reverts the color when mouse leaves
  });
</script>
```

In this example, when the mouse hovers over the `div`, the background color changes.

---

## 🧹 Removing Event Listeners

You can remove an event listener using `removeEventListener()`. This method works similarly to `addEventListener()` but requires that the function used is the same as the one originally passed.

### Syntax

```javascript
element.removeEventListener(event, function, useCapture);
```

---

### Example: Removing a Click Event

```html
<button id="myButton">Click Me!</button>

<script>
  const button = document.getElementById('myButton');
  
  function handleClick() {
    alert('Button clicked!');
  }
  
  button.addEventListener('click', handleClick);

  // Remove the click event listener
  button.removeEventListener('click', handleClick);
</script>
```

In this example, the click event listener is added and then removed, preventing the alert from showing when the button is clicked.

---

## 📚 Key Points

- Use `addEventListener()` to attach event handlers to DOM elements.
- Use `removeEventListener()` to remove event handlers.
- Event types can include `click`, `mouseover`, `keydown`, and more.
- Multiple event listeners can be attached to a single element for different events.

---

## 📚 Resources

- [MDN - addEventListener()](https://developer.mozilla.org/en-US/docs/Web/API/EventTarget/addEventListener)
- [MDN - removeEventListener()](https://developer.mozilla.org/en-US/docs/Web/API/EventTarget/removeEventListener)
