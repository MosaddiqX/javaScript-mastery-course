# 🛠️ Integrating GSAP with Other Libraries

One of the most powerful features of GSAP is its ability to seamlessly integrate with other libraries and frameworks. In this section, we’ll explore how to combine GSAP with HTML, CSS, and JavaScript, as well as how to integrate it with popular libraries and frameworks.

## 📜 Integrating GSAP with HTML and CSS

GSAP is designed to work effortlessly with regular HTML and CSS. You can animate any HTML element, adjust CSS properties, and even trigger animations based on user interactions.

### Example: Animating HTML and CSS Properties

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>GSAP Integration Example</title>
  <style>
    .box {
      width: 100px;
      height: 100px;
      background-color: red;
    }
  </style>
</head>
<body>

<div class="box"></div>

<script src="https://cdnjs.cloudflare.com/ajax/libs/gsap/3.9.1/gsap.min.js"></script>
<script>
  gsap.to(".box", {
    duration: 2,
    x: 300,
    rotation: 360
  });
</script>

</body>
</html>
```

In this example, we use GSAP to animate the `.box` element by moving it 300px to the right and rotating it by 360 degrees. You can animate any CSS property like `x`, `y`, `scale`, `rotation`, `opacity`, and more.

---

## 🔄 Integrating GSAP with JavaScript Frameworks

GSAP is highly compatible with popular JavaScript frameworks such as React, Vue.js, and Angular. Let’s look at a few examples:

### React Integration

GSAP can be used in a React component to animate elements in response to state changes, lifecycle methods, or user interactions.

#### Example: React Component with GSAP Animation

```javascript
import React, { useEffect } from 'react';
import gsap from 'gsap';

const MyComponent = () => {
  useEffect(() => {
    gsap.to(".box", { duration: 2, x: 300 });
  }, []);

  return <div className="box">Hello, GSAP!</div>;
};

export default MyComponent;
```

In this React example, GSAP is used within the `useEffect` hook to animate the `.box` when the component is mounted. The box will move 300px to the right.

### Vue.js Integration

GSAP can also be used in Vue.js components to animate DOM elements.

#### Example: Vue Component with GSAP Animation

```html
<template>
  <div class="box">Hello, Vue and GSAP!</div>
</template>

<script>
import { gsap } from "gsap";

export default {
  mounted() {
    gsap.to(".box", { duration: 2, y: 200 });
  }
};
</script>

<style scoped>
.box {
  width: 100px;
  height: 100px;
  background-color: green;
}
</style>
```

In this Vue.js example, the box element is animated to move 200px down when the component is mounted.

---

## ⚙️ Integrating GSAP with Other Libraries

GSAP also integrates well with other animation and interaction libraries such as:

- **ScrollMagic**: For scroll-triggered animations.
- **Three.js**: For animating 3D objects.
- **PixiJS**: For 2D WebGL rendering and animation.

For example, you can use GSAP to animate a 3D object created with Three.js:

```javascript
import * as THREE from 'three';
import { gsap } from 'gsap';

const scene = new THREE.Scene();
const camera = new THREE.PerspectiveCamera(75, window.innerWidth / window.innerHeight, 0.1, 1000);
const renderer = new THREE.WebGLRenderer();
renderer.setSize(window.innerWidth, window.innerHeight);
document.body.appendChild(renderer.domElement);

const geometry = new THREE.BoxGeometry();
const material = new THREE.MeshBasicMaterial({ color: 0x00ff00 });
const cube = new THREE.Mesh(geometry, material);
scene.add(cube);

camera.position.z = 5;

gsap.to(cube.rotation, { x: Math.PI * 2, duration: 5, repeat: -1, yoyo: true });

function animate() {
  requestAnimationFrame(animate);
  renderer.render(scene, camera);
}
animate();
```

In this Three.js example, we animate a cube's rotation using GSAP while rendering the scene with WebGL.

---

## 📌 Key Takeaways

- **GSAP with HTML/CSS**: You can animate any HTML element or CSS property.
- **GSAP with JavaScript Frameworks**: GSAP integrates seamlessly with React, Vue.js, Angular, and more.
- **GSAP with Other Libraries**: GSAP can be combined with libraries like ScrollMagic, Three.js, and PixiJS to create advanced animations and interactive effects.

In the next section, we’ll dive deeper into GSAP objects, methods, and how to use them for more advanced animations.
