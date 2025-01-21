# 💻 Project 1: Interactive To-Do List

## 🎯 Description and Objectives

In this project, we will create a simple yet functional To-Do list web application. The goal is to apply the DOM manipulation skills to dynamically add, delete, and edit tasks. This will also involve understanding how to handle user input, update the DOM, and store the tasks persistently using local storage.

## 📋 Steps to Complete Project 1

1. **Set up the basic HTML structure:**
   - Create a container for the To-Do list.
   - Add a text input field for new tasks.
   - Add a button to add tasks.
   - Display the list of tasks dynamically in the UI.

2. **Add Event Listeners:**
   - Attach event listeners to the "Add Task" button to capture user input and add the new task to the list.
   - Attach an event listener to each task to enable editing and deletion.

3. **Modify the DOM:**
   - Dynamically add new tasks to the list when the user submits a task.
   - Allow the user to delete tasks or mark them as completed.
   
4. **Store tasks persistently:**
   - Use `localStorage` to save tasks even after refreshing the page.
   - Retrieve tasks from `localStorage` and display them when the page loads.

5. **Enhance with CSS:**
   - Style the To-Do list for better user experience.
   - Add hover effects, background colors, and task completion styles.

---

## 🧑‍💻 Key Concepts and Techniques Applied

- **DOM Manipulation**: You will dynamically create and manipulate HTML elements (e.g., adding and removing tasks).
- **Event Handling**: Learn how to handle click events for adding, editing, and deleting tasks.
- **Local Storage**: Learn how to store data persistently across page reloads using `localStorage`.
- **CSS Styling**: Style the To-Do list for a polished, user-friendly experience.

---

## 📚 Example Code

```html
<!-- HTML Structure -->
<div id="app">
  <h1>To-Do List</h1>
  <input type="text" id="taskInput" placeholder="Enter a new task">
  <button id="addTaskBtn">Add Task</button>
  <ul id="taskList"></ul>
</div>

<script>
// JavaScript Code
const addButton = document.getElementById('addTaskBtn');
const taskInput = document.getElementById('taskInput');
const taskList = document.getElementById('taskList');

// Add task to the list
addButton.addEventListener('click', function() {
  const taskText = taskInput.value;
  if (taskText) {
    const li = document.createElement('li');
    li.textContent = taskText;
    taskList.appendChild(li);
    
    // Save to localStorage
    let tasks = JSON.parse(localStorage.getItem('tasks')) || [];
    tasks.push(taskText);
    localStorage.setItem('tasks', JSON.stringify(tasks));
    
    taskInput.value = ''; // Clear input
  }
});

// Load tasks from localStorage
window.onload = function() {
  const tasks = JSON.parse(localStorage.getItem('tasks')) || [];
  tasks.forEach(function(task) {
    const li = document.createElement('li');
    li.textContent = task;
    taskList.appendChild(li);
  });
};
</script>
```

---

## ✅ Outcome

By the end of this project, you will have created a functional To-Do list application with the following features:
- Users can add new tasks.
- Tasks can be deleted or edited.
- Tasks are saved and persist across page reloads.
- A clean and styled interface that makes use of DOM manipulation and local storage.

---

## 📚 Resources

- [MDN - DOM Manipulation](https://developer.mozilla.org/en-US/docs/Web/API/Document_Object_Model/Introduction)
- [MDN - localStorage](https://developer.mozilla.org/en-US/docs/Web/API/Window/localStorage)
