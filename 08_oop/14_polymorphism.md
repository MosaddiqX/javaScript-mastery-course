# 🧬 Polymorphism in JavaScript

**Polymorphism** is a key concept in Object-Oriented Programming (OOP) that allows objects of different classes to be treated as objects of a common superclass. The term **polymorphism** means "many shapes," and it allows methods to behave differently based on the object they are called on, even though they share the same name.

In JavaScript, polymorphism is achieved through method overriding and method overloading.

---

## 🔑 What is Polymorphism?

Polymorphism allows objects of different types to be treated as if they are objects of the same type. In practice, it means that the same method or function name can behave differently depending on which class or object it is invoked on.

### Types of Polymorphism:
- **Compile-time Polymorphism (Method Overloading)**: This occurs when multiple methods share the same name but differ in the number or type of parameters. JavaScript doesn't support compile-time polymorphism in a traditional sense, but we can still implement similar behaviors using default parameters or arguments.
  
- **Runtime Polymorphism (Method Overriding)**: This occurs when a subclass provides a specific implementation of a method already defined in its superclass. JavaScript relies heavily on runtime polymorphism via method overriding.

---

## 🧑‍🏫 Example: Method Overriding (Runtime Polymorphism)

In JavaScript, polymorphism is commonly implemented via method overriding. Here's an example using inheritance:

```javascript
class Animal {
  speak() {
    console.log("Animal makes a sound");
  }
}

class Dog extends Animal {
  speak() {
    console.log("Dog barks");
  }
}

class Cat extends Animal {
  speak() {
    console.log("Cat meows");
  }
}

let dog = new Dog();
let cat = new Cat();

dog.speak();  // Output: Dog barks
cat.speak();  // Output: Cat meows
```

In this example:
- The `Animal` class has a `speak()` method, and both `Dog` and `Cat` classes override this method.
- Even though both `Dog` and `Cat` share the `speak()` method name, they exhibit different behaviors when invoked. This is polymorphism in action.

---

## 👨‍🏫 Example: Using Polymorphism with Interfaces

Polymorphism is often used when multiple objects share the same method signature but implement it differently. In JavaScript, you can simulate an interface with classes.

```javascript
class Shape {
  draw() {
    throw "Method 'draw()' must be implemented.";
  }
}

class Circle extends Shape {
  draw() {
    console.log("Drawing a Circle");
  }
}

class Square extends Shape {
  draw() {
    console.log("Drawing a Square");
  }
}

function renderShape(shape) {
  shape.draw();  // Polymorphism in action
}

let circle = new Circle();
let square = new Square();

renderShape(circle);  // Output: Drawing a Circle
renderShape(square);  // Output: Drawing a Square
```

In this example:
- The `Shape` class serves as a "base" class, and the `draw()` method is overridden in both the `Circle` and `Square` classes.
- The `renderShape()` function takes any object of type `Shape` and calls its `draw()` method. This function works with different types of objects, showcasing polymorphism.

---

## 🛠️ Key Points About Polymorphism

- **Same Method Name, Different Behaviors**: Polymorphism allows methods to share the same name but have different behaviors depending on the object on which they are called.
- **Method Overriding**: A subclass can provide its own implementation of a method inherited from its superclass, changing how the method works.
- **Method Overloading in JavaScript**: While JavaScript doesn't support traditional method overloading, you can simulate it by using default parameters or handling different types of arguments within the method.

---

## 💡 Conclusion

Polymorphism is a crucial feature of Object-Oriented Programming, allowing for flexibility and extensibility in your code. It enables objects to be treated in a generic way, while still allowing different classes to provide their own specific behavior. In JavaScript, polymorphism is often implemented through **method overriding**, where subclasses provide their own implementation of methods inherited from parent classes.

By leveraging polymorphism, you can create more flexible, reusable, and maintainable code.

---

## 📚 Resources

- [MDN - Polymorphism in OOP](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Classes#Polymorphism)
- [JavaScript.info - Polymorphism](https://javascript.info/class-inheritance#polymorphism)
