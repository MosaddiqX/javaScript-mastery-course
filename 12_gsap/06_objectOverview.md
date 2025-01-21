# 🧰 Overview of GSAP Objects and Methods

In GSAP (GreenSock Animation Platform), animation is handled using **objects** like `Tween` and `Timeline`. These objects provide a wide array of methods and options to create powerful animations with ease.

In this section, we’ll take a closer look at GSAP's core objects and how to use them to create and manage animations.

---

## 🎬 Tween Object

A **Tween** is the basic unit of animation in GSAP. It is used to animate a specific set of properties of an element over a period of time.

### Creating a Tween

To create a basic tween, use the `gsap.to()` or `gsap.from()` method. Both methods return a Tween instance, allowing you to control the animation.

#### Example: Simple Tween

```javascript
gsap.to(".box", {
  duration: 2,
  x: 300,
  y: 200,
  opacity: 0.5
});
```

In this example:
- We animate the `.box` element to move 300px along the X-axis, 200px along the Y-axis, and reduce its opacity to 0.5 over 2 seconds.
- `gsap.to()` is a shorthand for creating animations where the properties of the target element move from its current state to the defined values.

---

### Tween Methods

Here are some key methods and options you can use with a `Tween`:

- `to()`: Animates an element from its current state to the specified values.
- `from()`: Animates an element from the specified values to its current state.
- `fromTo()`: Animates an element from a defined start state to a target state.
- `staggerTo()`: Staggers animations for multiple elements.
- `pause()`, `resume()`, `restart()`: Control the playback of the tween.

#### Example: Using `fromTo()`

```javascript
gsap.fromTo(".box", 
  { x: 0, y: 0 }, 
  { x: 300, y: 200, duration: 2 }
);
```

This example animates `.box` from an initial position of (0, 0) to the target position (300, 200).

---

## ⏳ Timeline Object

A **Timeline** is a collection of tweens that can be played sequentially or simultaneously. Timelines allow you to manage multiple animations, making it easy to create complex animation sequences.

### Creating a Timeline

You can create a timeline using `gsap.timeline()`, which allows you to chain multiple tweens together.

#### Example: Simple Timeline

```javascript
const tl = gsap.timeline();
tl.to(".box", { duration: 1, x: 300 });
tl.to(".box", { duration: 1, y: 200 });
tl.to(".box", { duration: 1, opacity: 0 });
```

In this example, the `tl` timeline contains three tweens:
- The first moves the `.box` 300px along the X-axis.
- The second moves the `.box` 200px along the Y-axis.
- The third reduces the `.box` opacity to 0.

### Timeline Methods

- `add()`: Adds tweens to the timeline at a specific point in time.
- `play()`, `pause()`, `reverse()`: Control the playback of the timeline.
- `seek()`: Jumps to a specific point in the timeline.
- `repeat()`, `yoyo()`: Control how many times the animation repeats and whether it reverses on each cycle.

#### Example: Adding Tweens to a Timeline

```javascript
const tl = gsap.timeline();
tl.to(".box", { duration: 1, x: 300 })
  .to(".box", { duration: 1, y: 200 })
  .to(".box", { duration: 1, opacity: 0 });
```

This example uses chaining to add multiple tweens to the timeline in a cleaner and more readable manner.

---

## 🔗 Key Takeaways

- **Tween Object**: The basic unit for animating properties of elements. Use methods like `to()`, `from()`, and `fromTo()` to control animations.
- **Timeline Object**: A collection of tweens that can be played sequentially or simultaneously. Use `add()`, `play()`, and `pause()` to manage animations.

Timelines are especially useful for complex animations, where you want to create multi-step sequences with precise control over the timing of each animation.

In the next section, we’ll explore the `set()` method, which allows you to quickly set the initial state of an element before animating it.
