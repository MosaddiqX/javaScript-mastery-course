# 🗂️ Project 6: Task Management System with a Database

## 🎯 Description and Objectives

In this project, you will create a **Task Management System** that allows users to:
- Create, update, delete, and mark tasks as completed.
- Save tasks to a **database** (e.g., using **MongoDB** or **SQL**).
- Use **Express** and **Node.js** for the backend, and **MongoDB** (or another database) for persistent data storage.

Key features include:
- User authentication (e.g., with **JWT**)
- CRUD operations for tasks
- Database integration to store tasks
- A simple front-end using **HTML**, **CSS**, and **JavaScript**
- Task categorization (e.g., pending, completed, etc.)
  
## 📋 Steps to Complete Project 6

1. **Set up the backend environment:**
   - Install **Node.js** and set up a basic **Express** server.
   - Set up the **MongoDB** (or SQL) database to store tasks.
   - Implement **User Authentication** using JWT (JSON Web Tokens).
   
2. **Create RESTful API Endpoints:**
   - Implement routes for CRUD operations on tasks:
     - `POST /tasks`: Create a new task.
     - `GET /tasks`: Retrieve all tasks.
     - `GET /tasks/:id`: Retrieve a single task.
     - `PUT /tasks/:id`: Update a task.
     - `DELETE /tasks/:id`: Delete a task.
   
3. **Connect the frontend with the backend:**
   - Set up the frontend to allow users to create, view, and update tasks.
   - Use **Fetch API** or **Axios** to interact with the backend API.
   
4. **Implement Task Categories:**
   - Allow users to categorize tasks (e.g., pending, completed, in-progress).
   - Add buttons to filter tasks by category.

5. **User Authentication:**
   - Implement a simple login and signup system with JWT authentication.
   - Secure the routes so that only authenticated users can perform CRUD operations on tasks.

6. **Styling:**
   - Apply CSS to create a user-friendly interface.
   - Ensure the application is responsive for both desktop and mobile users.

7. **Error Handling and Validation:**
   - Implement server-side validation for tasks (e.g., non-empty titles).
   - Add error handling for invalid inputs and missing data.

8. **Deploy the Application:**
   - Host the backend on a service like **Heroku** or **Vercel**.
   - Host the frontend on **Netlify** or another static hosting service.
   
---

## 🧑‍💻 Key Concepts and Techniques Applied

- **Express.js**: Learn how to build RESTful APIs with Express.
- **MongoDB/SQL Database**: Store and retrieve tasks with a database.
- **JWT Authentication**: Secure routes and provide user authentication with JWT tokens.
- **CRUD Operations**: Implement basic operations like Create, Read, Update, and Delete for tasks.
- **API Integration**: Connect the frontend with backend APIs using **Fetch API** or **Axios**.
- **Task Management Logic**: Implement logic for task categorization, filtering, and status updates.
- **Responsive Design**: Design a UI that works across different devices.

---

## 📚 Example Code

### Backend: Express + MongoDB

```javascript
// server.js
const express = require('express');
const mongoose = require('mongoose');
const bodyParser = require('body-parser');
const jwt = require('jsonwebtoken');
const app = express();

// Connect to MongoDB
mongoose.connect('mongodb://localhost/taskdb', { useNewUrlParser: true, useUnifiedTopology: true });

// Define Task schema and model
const taskSchema = new mongoose.Schema({
  title: String,
  description: String,
  status: { type: String, default: 'pending' },
  createdAt: { type: Date, default: Date.now },
});

const Task = mongoose.model('Task', taskSchema);

// Middleware for parsing JSON
app.use(bodyParser.json());

// User authentication middleware
function authenticateToken(req, res, next) {
  const token = req.header('Authorization')?.split(' ')[1];
  if (!token) return res.status(403).send('Access denied.');
  jwt.verify(token, 'your_jwt_secret', (err, user) => {
    if (err) return res.status(403).send('Invalid token.');
    req.user = user;
    next();
  });
}

// Create a new task
app.post('/tasks', authenticateToken, (req, res) => {
  const { title, description } = req.body;
  const newTask = new Task({ title, description });
  newTask.save((err, task) => {
    if (err) return res.status(500).send('Error saving task.');
    res.status(201).json(task);
  });
});

// Get all tasks
app.get('/tasks', authenticateToken, (req, res) => {
  Task.find({}, (err, tasks) => {
    if (err) return res.status(500).send('Error retrieving tasks.');
    res.status(200).json(tasks);
  });
});

// Update a task
app.put('/tasks/:id', authenticateToken, (req, res) => {
  const { id } = req.params;
  const { title, description, status } = req.body;
  Task.findByIdAndUpdate(id, { title, description, status }, { new: true }, (err, task) => {
    if (err) return res.status(500).send('Error updating task.');
    res.status(200).json(task);
  });
});

// Delete a task
app.delete('/tasks/:id', authenticateToken, (req, res) => {
  const { id } = req.params;
  Task.findByIdAndDelete(id, (err) => {
    if (err) return res.status(500).send('Error deleting task.');
    res.status(200).send('Task deleted.');
  });
});

// Start server
app.listen(5000, () => console.log('Server is running on http://localhost:5000'));
```

### Frontend: HTML + JavaScript

```html
<!-- index.html -->
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Task Management</title>
  <style>
    /* Basic styles */
    body { font-family: Arial, sans-serif; padding: 20px; }
    #tasks { margin-top: 20px; }
    #tasks li { padding: 10px; border: 1px solid #ccc; margin-bottom: 10px; }
  </style>
</head>
<body>

<h1>Task Management</h1>
<div>
  <input type="text" id="taskTitle" placeholder="Task Title">
  <textarea id="taskDescription" placeholder="Task Description"></textarea>
  <button id="addTaskBtn">Add Task</button>
</div>

<ul id="tasks"></ul>

<script>
  const addTaskBtn = document.getElementById('addTaskBtn');
  const taskTitleInput = document.getElementById('taskTitle');
  const taskDescriptionInput = document.getElementById('taskDescription');
  const tasksList = document.getElementById('tasks');

  // Add task to the database
  addTaskBtn.addEventListener('click', async () => {
    const title = taskTitleInput.value.trim();
    const description = taskDescriptionInput.value.trim();
    if (title && description) {
      const response = await fetch('http://localhost:5000/tasks', {
        method: 'POST',
        headers: {
          'Content-Type': 'application/json',
          'Authorization': 'Bearer your_jwt_token_here',
        },
        body: JSON.stringify({ title, description }),
      });

      const newTask = await response.json();
      if (response.ok) {
        const li = document.createElement('li');
        li.textContent = `${newTask.title}: ${newTask.description}`;
        tasksList.appendChild(li);
      }
    }
  });

  // Fetch and display tasks from the database
  async function loadTasks() {
    const response = await fetch('http://localhost:5000/tasks', {
      headers: { 'Authorization': 'Bearer your_jwt_token_here' }
    });
    const tasks = await response.json();
    tasks.forEach(task => {
      const li = document.createElement('li');
      li.textContent = `${task.title}: ${task.description}`;
      tasksList.appendChild(li);
    });
  }

  // Load tasks on page load
  loadTasks();
</script>

</body>
</html>
```

---

## 🧑‍💻 Key Concepts and Techniques Applied

- **Express.js & MongoDB**: Create a RESTful API that interacts with a database to store and manage tasks.
- **JWT Authentication**: Implement a user login system using JSON Web Tokens to secure the API.
- **CRUD Operations**: Implement the ability to create, read, update, and delete tasks.
- **Task Filtering & Categorization**: Implement functionality to categorize tasks (e.g., completed, pending).
- **Frontend-Backend Integration**: Use **Fetch API** to interact with the backend and display tasks dynamically.

---

## 📚 Resources

- [Express.js Documentation](https://expressjs.com/)
- [MongoDB](https://www.mongodb.com/)
- [JWT Authentication](https://jwt.io/)

---

### Instructions:
- Set up the backend with Express and MongoDB.
- Implement authentication using JWT.
- Create the frontend with HTML, CSS, and JavaScript to interact with the backend API.
