# 🔒 Encapsulation in JavaScript

**Encapsulation** is one of the fundamental concepts in Object-Oriented Programming (OOP). It refers to the bundling of data (properties) and methods that operate on that data within a single unit or class. Encapsulation helps to restrict access to certain details of an object, providing a controlled interface for interaction.

In JavaScript, encapsulation can be achieved using **private** and **public** members, which are accessible only in certain ways.

---

## 🛡️ What is Encapsulation?

Encapsulation refers to the practice of restricting access to certain object components and only exposing a controlled interface. It hides the internal state of an object and only allows access to it through well-defined methods.

### Key Benefits of Encapsulation:
- **Data Protection**: Keeps data safe from unauthorized access or modification.
- **Code Modularity**: Makes the code more modular and easier to maintain by separating the internal workings of an object.
- **Controlled Access**: Allows access to internal data only through specific methods, maintaining control over how the data is modified.

---

## 🔐 Encapsulation in JavaScript

In JavaScript, encapsulation is primarily implemented using **private fields** and **getter/setter methods**.

### Example of Encapsulation with Private Fields

```javascript
class BankAccount {
  #balance; // Private property

  constructor(accountNumber, initialBalance) {
    this.accountNumber = accountNumber;
    this.#balance = initialBalance; // Private balance
  }

  // Getter Method
  getBalance() {
    return this.#balance;
  }

  // Setter Method
  deposit(amount) {
    if (amount > 0) {
      this.#balance += amount;
      console.log(`Deposited $${amount}`);
    } else {
      console.log('Deposit amount must be positive.');
    }
  }

  withdraw(amount) {
    if (amount > 0 && amount <= this.#balance) {
      this.#balance -= amount;
      console.log(`Withdrew $${amount}`);
    } else {
      console.log('Insufficient funds or invalid amount.');
    }
  }
}

let account = new BankAccount('12345', 1000);

console.log(account.getBalance()); // Output: 1000
account.deposit(500);              // Output: Deposited $500
account.withdraw(300);             // Output: Withdrew $300
console.log(account.getBalance()); // Output: 1200

// Attempting to access private balance directly will result in an error
// console.log(account.#balance);  // SyntaxError: Private field '#balance' must be declared in an enclosing class
```

In this example:
- The **balance** is a private property, ensuring that it cannot be modified directly from outside the class.
- The **deposit()** and **withdraw()** methods are used to manipulate the balance, offering controlled access.
- The **getter** method `getBalance()` provides safe access to the private balance.

---

## 🏗️ Achieving Encapsulation with Getter/Setter Methods

Although JavaScript provides the `#` syntax for private fields, you can also use **getter** and **setter** methods to encapsulate properties, even without private fields.

### Example with Getter/Setter Methods

```javascript
class Rectangle {
  constructor(width, height) {
    this._width = width;  // Protected property (by convention)
    this._height = height; // Protected property (by convention)
  }

  // Getter Method
  getArea() {
    return this._width * this._height;
  }

  // Setter Methods
  setWidth(width) {
    if (width > 0) {
      this._width = width;
    }
  }

  setHeight(height) {
    if (height > 0) {
      this._height = height;
    }
  }
}

let rectangle = new Rectangle(10, 5);

console.log(rectangle.getArea()); // Output: 50
rectangle.setWidth(15);
console.log(rectangle.getArea()); // Output: 75
```

In this example:
- We use **getter** and **setter** methods to control how the `width` and `height` properties are modified and accessed.
- The setter methods ensure that only valid values can be assigned to the properties.

---

## 🚧 Why Encapsulation is Important

1. **Data Integrity**: By controlling how properties are accessed and modified, we can ensure the object's state remains valid and consistent.
2. **Flexibility**: Encapsulation allows for flexibility in changing the internal implementation of a class without affecting how external code interacts with it.
3. **Security**: Sensitive data (such as account balances, personal information, etc.) can be kept private, reducing the risk of misuse or accidental modification.

---

## 💡 Encapsulation in Practice

Here are some common real-world scenarios where encapsulation is useful:

1. **Bank Account**: A class representing a bank account should restrict direct access to the account balance. Access should be provided only through controlled methods like `deposit()` and `withdraw()`.
2. **User Profiles**: Personal information (e.g., passwords, email addresses) should be kept private within an object, with access provided only through getter/setter methods or methods that manage privacy.
3. **Game Settings**: In a game, certain game settings like health points, levels, etc., should be controlled by getter and setter methods to ensure the game state remains valid.

---

## 🔗 Conclusion

Encapsulation is a powerful concept that helps keep the internals of an object hidden while still providing a way to interact with it through well-defined methods. It enhances the maintainability, security, and flexibility of your code. In JavaScript, we can use **private fields**, **getter/setter methods**, and **class constructors** to achieve encapsulation.

---

## 📚 Resources

- [MDN - Classes](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Classes)
- [JavaScript.info - Encapsulation](https://javascript.info/class-private-fields)

