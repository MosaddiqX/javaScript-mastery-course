# 💻 Project 3: To-Do List with User Authentication

## 🎯 Description and Objectives

In this project, you'll build a **To-Do List** application where users can sign up, log in, and manage their to-do items. The app will store tasks and user data persistently, and only authenticated users can view and update their tasks.

Key features include:
- User authentication with login/signup functionality
- Add, edit, and delete tasks
- Persistent data storage (using local storage or a back-end server)

## 📋 Steps to Complete Project 3

1. **Create a user authentication system:**
   - Set up basic sign-up and login forms.
   - Use local storage or a simple back-end server to persist user information (such as username and password).
   - Implement authentication logic to allow users to log in and log out.

2. **Build the To-Do List Interface:**
   - Create a simple UI with fields for adding tasks, and buttons to edit or delete them.
   - Display the tasks in a list and allow the user to interact with them.

3. **Store tasks persistently:**
   - After authentication, allow users to add, edit, and delete tasks.
   - Store the tasks in `localStorage` or on the server (if you choose to use a back-end service).
   - Ensure the tasks persist across sessions, so when users log back in, they can see their previous tasks.

4. **Task Management Features:**
   - Add a feature to mark tasks as complete or incomplete (toggle task completion).
   - Allow users to filter tasks by their completion status (completed or pending).

5. **Error Handling and Validation:**
   - Handle errors such as empty inputs for tasks and authentication issues (e.g., incorrect login credentials).
   - Show user-friendly error messages in case of invalid actions.

---

## 🧑‍💻 Key Concepts and Techniques Applied

- **User Authentication**: Learn how to implement login and sign-up forms with basic authentication (you can use `localStorage` or a back-end server for this).
- **Local Storage**: Use `localStorage` or another method for persistent storage to keep user tasks even after page reloads.
- **DOM Manipulation**: Dynamically update the UI when tasks are added, edited, or deleted.
- **Form Validation**: Implement form validation to ensure correct inputs for user registration and tasks.
- **Event Handling**: Add event listeners to handle user interactions such as adding tasks, toggling completion status, and deleting tasks.

---

## 📚 Example Code

```html
<!-- HTML Structure -->
<div id="authForm">
  <h2>Sign Up</h2>
  <input type="text" id="username" placeholder="Enter Username">
  <input type="password" id="password" placeholder="Enter Password">
  <button id="signupBtn">Sign Up</button>
  <button id="loginBtn">Log In</button>
</div>

<div id="todoApp" style="display: none;">
  <h1>To-Do List</h1>
  <input type="text" id="taskInput" placeholder="Enter a task">
  <button id="addTaskBtn">Add Task</button>
  <ul id="taskList"></ul>
  <button id="logoutBtn">Log Out</button>
</div>

<script>
// JavaScript Code
let currentUser = localStorage.getItem('username');

// Show login/signup form or To-Do app based on authentication status
if (currentUser) {
  document.getElementById('authForm').style.display = 'none';
  document.getElementById('todoApp').style.display = 'block';
} else {
  document.getElementById('authForm').style.display = 'block';
  document.getElementById('todoApp').style.display = 'none';
}

// Sign up logic
document.getElementById('signupBtn').addEventListener('click', function() {
  const username = document.getElementById('username').value;
  const password = document.getElementById('password').value;
  if (username && password) {
    localStorage.setItem('username', username);
    localStorage.setItem('password', password);  // Simple approach (In production, use encryption)
    alert('User signed up successfully!');
    currentUser = username;
    document.getElementById('authForm').style.display = 'none';
    document.getElementById('todoApp').style.display = 'block';
  } else {
    alert('Please enter valid credentials!');
  }
});

// Log in logic
document.getElementById('loginBtn').addEventListener('click', function() {
  const username = document.getElementById('username').value;
  const password = document.getElementById('password').value;
  if (localStorage.getItem('username') === username && localStorage.getItem('password') === password) {
    alert('Logged in successfully!');
    currentUser = username;
    document.getElementById('authForm').style.display = 'none';
    document.getElementById('todoApp').style.display = 'block';
  } else {
    alert('Invalid credentials!');
  }
});

// Task management logic
document.getElementById('addTaskBtn').addEventListener('click', function() {
  const taskInput = document.getElementById('taskInput').value;
  if (taskInput) {
    const taskList = JSON.parse(localStorage.getItem(currentUser + '_tasks')) || [];
    taskList.push({ task: taskInput, completed: false });
    localStorage.setItem(currentUser + '_tasks', JSON.stringify(taskList));
    renderTasks();
    document.getElementById('taskInput').value = '';
  }
});

// Rendering tasks
function renderTasks() {
  const taskList = JSON.parse(localStorage.getItem(currentUser + '_tasks')) || [];
  const taskListElement = document.getElementById('taskList');
  taskListElement.innerHTML = '';
  taskList.forEach((task, index) => {
    const li = document.createElement('li');
    li.textContent = task.task;
    if (task.completed) {
      li.style.textDecoration = 'line-through';
    }
    li.addEventListener('click', function() {
      task.completed = !task.completed;
      taskList[index] = task;
      localStorage.setItem(currentUser + '_tasks', JSON.stringify(taskList));
      renderTasks();
    });
    taskListElement.appendChild(li);
  });
}

// Log out logic
document.getElementById('logoutBtn').addEventListener('click', function() {
  localStorage.removeItem('username');
  localStorage.removeItem('password');
  currentUser = null;
  document.getElementById('authForm').style.display = 'block';
  document.getElementById('todoApp').style.display = 'none';
});
</script>
```

---

## ✅ Outcome

By the end of this project, you will have built a **To-Do List** app with the following features:
- **User Authentication**: Sign-up and login functionality to ensure that only authenticated users can manage their tasks.
- **Task Management**: Add, delete, and toggle the completion status of tasks.
- **Persistent Data**: Tasks are saved in `localStorage` and persist across page reloads.
- **Error Handling**: Handle invalid login/signup credentials and empty task input.
- **UI Updates**: The UI dynamically updates to reflect the user's tasks and login state.

---

## 📚 Resources

- [MDN - Local Storage](https://developer.mozilla.org/en-US/docs/Web/API/Window/localStorage)
- [MDN - JavaScript Event Listeners](https://developer.mozilla.org/en-US/docs/Web/API/EventTarget/addEventListener)
- [MDN - Form Validation](https://developer.mozilla.org/en-US/docs/Learn/Forms/Form_validation)

---

### Instructions:
- Replace or enhance the authentication and task handling logic as needed.