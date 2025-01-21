# 🛠️ Setting Up GSAP in Your Project

Before we dive into animating with GSAP, it's important to know how to properly set it up in your project. Whether you are working on a simple webpage or a complex app, GSAP can be easily integrated.

## 📦 Installation Methods

There are multiple ways to include GSAP in your project. You can use a **CDN**, **npm**, or even **download** the library directly. Here are the most common methods:

---

### 1. **Using CDN**

The fastest way to get started with GSAP is by linking it directly from a Content Delivery Network (CDN). This method doesn’t require any installation and is great for simple projects.

Add this `<script>` tag in the `<head>` or at the end of the `<body>` tag of your HTML:

```html
<!-- GSAP CDN link -->
<script src="https://cdnjs.cloudflare.com/ajax/libs/gsap/3.9.1/gsap.min.js"></script>
```

Once this script is included, you can immediately start using GSAP in your JavaScript code.

---

### 2. **Using npm (Node Package Manager)**

If you're working with a more complex project and using a build tool like **Webpack**, **Parcel**, or **Vite**, you can install GSAP via npm.

To install GSAP:

```bash
npm install gsap
```

After installation, you can import GSAP into your JavaScript files and start using it like this:

```javascript
// ES6 import syntax
import gsap from "gsap";

// Basic animation example
gsap.to(".box", {
  duration: 1,
  x: 100
});
```

If you're using CommonJS, you can require it like this:

```javascript
const gsap = require("gsap");
```

---

### 3. **Using Yarn**

If you're using **Yarn** as your package manager, you can install GSAP with this command:

```bash
yarn add gsap
```

Just like with npm, you can then import GSAP in your JavaScript files.

---

## 🔧 Setting Up in a Project

Regardless of which method you use, once you have GSAP installed or linked, you can start using it right away. Here's a quick overview of how to get started with the basic setup:

### Example: Setting Up a Simple Animation

Let's create a basic webpage that animates a box:

1. **Create your HTML structure**:

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>GSAP Animation</title>
  <script src="https://cdnjs.cloudflare.com/ajax/libs/gsap/3.9.1/gsap.min.js"></script> <!-- GSAP CDN -->
</head>
<body>
  <div class="box"></div>
  <script src="script.js"></script> <!-- Your custom JavaScript -->
</body>
</html>
```

2. **Style the `.box` element**:

```css
/* Basic styling for the box */
.box {
  width: 100px;
  height: 100px;
  background-color: #3498db;
  position: absolute;
  top: 50px;
  left: 50px;
}
```

3. **Create a simple animation in `script.js`**:

```javascript
// Basic GSAP animation
gsap.to(".box", {
  duration: 2,  // The animation will take 2 seconds
  x: 300,       // Move the box 300px to the right
  opacity: 0.5,  // Change the opacity to 0.5
  ease: "power1.inOut"  // Apply easing for smooth animation
});
```

Once this setup is in place, simply open your HTML file in the browser, and the `.box` element will animate as defined in your GSAP code.

---

## 💡 Alternative Setups

- If you prefer to use a **build tool** like Webpack, you can bundle your GSAP animations with other assets for more advanced workflows.
- You can also use **GSAP with React, Vue, or Angular** by installing it via npm and integrating it directly into your component logic.

---

## ✅ Key Takeaways

- **CDN** is quick and easy for simple projects.
- **npm** and **Yarn** are ideal for more complex projects using build tools.
- GSAP can be set up in just a few steps, and you can start animating right away!

In the next section, we’ll dive deeper into animation techniques, where you can learn how to create advanced animations with GSAP.
