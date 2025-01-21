# 🧩 Logical Operations in JavaScript

Logical operators allow you to combine or invert conditions, making them essential for control flow in your programs. The most common logical operators are **AND (&&)**, **OR (||)**, and **NOT (!)**.

---

## 🔥 AND (`&&`) Operator

The `&&` (AND) operator returns `true` if **both** operands are true. If either of the operands is false, it returns `false`.

### Syntax:
```javascript
condition1 && condition2
```

### Example: Checking Multiple Conditions

```javascript
let age = 20;
let hasID = true;

if (age >= 18 && hasID) {
  console.log("You are allowed to enter.");
} else {
  console.log("Access denied.");
}
```

### Output:
```
You are allowed to enter.
```

---

## 🚀 OR (`||`) Operator

The `||` (OR) operator returns `true` if **at least one** of the operands is true. It returns `false` only if both operands are false.

### Syntax:
```javascript
condition1 || condition2
```

### Example: Checking if Either Condition is True

```javascript
let isWeekend = true;
let isHoliday = false;

if (isWeekend || isHoliday) {
  console.log("You can relax today.");
} else {
  console.log("It's a workday.");
}
```

### Output:
```
You can relax today.
```

---

## 🧩 NOT (`!`) Operator

The `!` (NOT) operator inverts the boolean value of the operand. If the operand is true, it returns false, and vice versa.

### Syntax:
```javascript
!condition
```

### Example: Inverting a Condition

```javascript
let isRainy = false;

if (!isRainy) {
  console.log("You don't need an umbrella.");
} else {
  console.log("Take your umbrella!");
}
```

### Output:
```
You don't need an umbrella.
```

---

## 🚀 Combining Logical Operators

You can combine multiple logical operators to create more complex conditions.

```javascript
let isWeekend = true;
let isHoliday = false;
let isSunny = true;

if ((isWeekend || isHoliday) && isSunny) {
  console.log("Perfect day for a picnic!");
} else {
  console.log("Maybe another day.");
}
```

### Output:
```
Perfect day for a picnic!
```

---

## 🧑‍💻 Example: Checking Multiple Conditions

### `script.js`
```javascript
let username = "Alice";
let password = "secure123";

if (username === "Alice" && password === "secure123") {
  console.log("Welcome back, Alice!");
} else {
  console.log("Invalid credentials.");
}
```

### Output:
```
Welcome back, Alice!
```

---

## 💡 Key Takeaways
1. **AND (`&&`) Operator**: Returns `true` if both conditions are true.
2. **OR (`||`) Operator**: Returns `true` if at least one condition is true.
3. **NOT (`!`) Operator**: Inverts the boolean value of a condition.
4. **Combining Operators**: You can combine logical operators to form more complex conditions.

---

### 🔗 Resources
- [MDN: Logical operators](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Logical_Operators)
- [JavaScript.info: Logical Operators](https://javascript.info/logical-operators)

---

### 🎉 Recap
Logical operators are powerful tools for combining multiple conditions. Use `&&` to ensure all conditions are true, `||` to check if any condition is true, and `!` to invert a condition. Mastering these operators is crucial for controlling the flow of your program.

