# ⏱️ GSAP Timelines: Managing Sequences of Animations

Timelines in GSAP provide a powerful way to control sequences of animations. Instead of animating elements one at a time, a timeline allows you to group animations together and control them as a whole. This makes creating complex animation sequences much easier.

In this section, we will cover how to create and manage timelines, as well as how to add and control animations within them.

---

## 📜 What is a Timeline?

A Timeline is a special object in GSAP that helps you organize multiple tweens and other timelines. It allows you to control the sequencing, timing, and execution order of your animations, all while offering methods to play, pause, or reverse the entire sequence.

### Creating a Basic Timeline

You can create a timeline using the `gsap.timeline()` method. Once you have a timeline, you can add animations to it using `.to()`, `.from()`, `.fromTo()`, etc.

### Example

```javascript
let tl = gsap.timeline();

tl.to(".box1", { duration: 1, x: 100 })
  .to(".box2", { duration: 1, x: 200 });
```

In this example:
- The animation of `.box1` runs first, and `.box2` starts immediately after it.
- Both elements move along the x-axis within 1 second each.

---

## ⏳ Controlling Timelines

You can control the entire timeline, just like you would with a single tween. Methods like `play()`, `pause()`, `reverse()`, and `seek()` apply to timelines as well.

### Example

```javascript
let tl = gsap.timeline({ paused: true });

tl.to(".box", { duration: 2, x: 300 })
  .to(".box", { duration: 2, y: 200 });

document.querySelector("#startButton").addEventListener("click", () => {
  tl.play(); // Starts the timeline when the button is clicked
});
```

In this example:
- The timeline is initially paused, and the animations will begin when the button is clicked.

---

## 🎯 Adding Staggered Animations to Timelines

You can add staggered animations to timelines to animate multiple elements in a sequence, one after another, with a delay between them.

### Example

```javascript
let tl = gsap.timeline();

tl.staggerTo(".box", 1, { x: 100 }, 0.2); // Staggers the x movement with a 0.2 second delay
```

In this example:
- `.box` elements are staggered with a 0.2-second delay between each one.

---

## 🔁 Nested Timelines

You can also nest timelines inside other timelines, allowing you to create complex, multi-layered animation sequences.

### Example

```javascript
let mainTimeline = gsap.timeline();

let nestedTimeline = gsap.timeline();

nestedTimeline.to(".box1", { duration: 1, x: 100 })
              .to(".box1", { duration: 1, y: 100 });

mainTimeline.add(nestedTimeline)  // Adds the nested timeline
              .to(".box2", { duration: 1, x: 200 });
```

In this example:
- The nested timeline animates `.box1`, and after that, the main timeline animates `.box2`.
- You can manage both timelines with ease.

---

## ⏲️ Delaying and Controlling Timeline Start Times

You can delay the start of a timeline or any animation within it using the `delay()` method. This allows you to sync animations or create time-based sequences.

### Example

```javascript
let tl = gsap.timeline({ delay: 1 }); // Delays the entire timeline by 1 second

tl.to(".box", { duration: 2, x: 100 });
```

In this example:
- The entire timeline will start 1 second after the page loads.

---

## 📅 Key Methods for Timelines

Here are some of the key methods you can use to control and manage timelines:

- `play()`: Starts the timeline from the current position or the beginning.
- `pause()`: Pauses the timeline at its current position.
- `reverse()`: Reverses the timeline, playing it backward.
- `seek(time)`: Jumps to a specific time in the timeline.
- `add()`: Adds an animation (or another timeline) to the timeline.
- `staggerTo()`: Staggers animations for multiple elements.
- `delay()`: Sets a delay before the timeline starts.

---

## 💡 Key Takeaways

- **Timelines** allow you to group multiple animations together and control them as a single entity.
- **Controlling Timelines**: Use methods like `play()`, `pause()`, `reverse()`, and `seek()` to control your timeline’s behavior.
- **Staggered Animations**: Create staggering effects with `staggerTo()` to animate multiple elements in sequence.
- **Nested Timelines**: Nest timelines within each other to create complex animation sequences.
- **Delays**: Use the `delay()` method to control when your timeline starts or when an animation is delayed.

Timelines provide more flexibility and control than individual tweens, making them essential for complex animation sequences!

Next, we’ll dive into **Unique Animations**, where you’ll learn how to create advanced and custom animations in GSAP!
