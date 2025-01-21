# 💬 Project 5: Real-time Chat Application using WebSockets

## 🎯 Description and Objectives

In this project, you will create a **Real-time Chat Application** that allows users to send and receive messages instantly without needing to refresh the page. The chat will use **WebSockets** to create a persistent, two-way connection between the client and the server for real-time communication.

Key features include:
- User authentication and login
- Real-time message exchange
- Displaying messages in a chat window
- Displaying the list of online users

## 📋 Steps to Complete Project 5

1. **Set up the project structure:**
   - Create a basic HTML, CSS, and JavaScript setup for the chat app.
   - Design the layout for the chat window, message input, and user list.
   
2. **WebSocket Server Setup:**
   - Use **Node.js** and **WebSocket library** (e.g., `ws`) to create a WebSocket server.
   - The server will handle connections, messages, and broadcast them to connected clients in real time.

3. **Client-side WebSocket Integration:**
   - Create a WebSocket client in JavaScript to connect to the server.
   - Implement logic to send messages to the server and display messages in the chat window.
   
4. **User Authentication:**
   - Implement a simple login system where users can authenticate themselves by entering a username.
   - Save the username on the client side and send it as part of the WebSocket connection.

5. **Real-time Messaging:**
   - Enable the client to send messages in real time.
   - When a message is sent, it will be broadcasted to all connected clients.
   - Implement a system for users to see incoming messages from others.

6. **Online User List:**
   - Display a list of online users in the chat.
   - Update the list dynamically when a user connects or disconnects from the chat.

7. **Styling:**
   - Apply CSS to make the chat window visually appealing.
   - Make sure the layout is responsive and mobile-friendly.

8. **Error Handling:**
   - Handle possible WebSocket errors and display relevant messages to the user if something goes wrong.

---

## 🧑‍💻 Key Concepts and Techniques Applied

- **WebSocket Communication**: Learn how to set up a WebSocket server and client to enable real-time messaging.
- **Real-time Updates**: Implement real-time data exchange between the client and server.
- **User Authentication**: Create a basic authentication system to track users.
- **DOM Manipulation**: Dynamically update the chat UI as messages are sent and received.
- **Event Handling**: Use events to handle user input, WebSocket events, and updates to the UI.
- **Responsive Design**: Ensure the chat application works well on both desktop and mobile devices.

---

## 📚 Example Code

### Client-Side (HTML + JavaScript)

```html
<!-- index.html -->
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Real-time Chat App</title>
    <style>
        /* Basic styles for chat window */
        body { font-family: Arial, sans-serif; margin: 0; padding: 0; }
        #chat-container { width: 100%; max-width: 500px; margin: 50px auto; border: 1px solid #ccc; padding: 10px; }
        #message-list { list-style-type: none; padding: 0; }
        #message-list li { margin-bottom: 10px; }
        input[type="text"] { width: 80%; padding: 10px; }
        button { padding: 10px; }
    </style>
</head>
<body>

<div id="chat-container">
    <h2>Real-time Chat</h2>
    <div>
        <input type="text" id="username" placeholder="Enter your username">
        <button id="login-btn">Login</button>
    </div>

    <div id="chat-area" style="display:none;">
        <ul id="message-list"></ul>
        <input type="text" id="message-input" placeholder="Type a message...">
        <button id="send-btn">Send</button>
    </div>
</div>

<script>
// JavaScript code
let username = '';
let ws;

// Elements
const loginBtn = document.getElementById('login-btn');
const usernameInput = document.getElementById('username');
const chatArea = document.getElementById('chat-area');
const messageList = document.getElementById('message-list');
const messageInput = document.getElementById('message-input');
const sendBtn = document.getElementById('send-btn');

// Event listener for login button
loginBtn.addEventListener('click', () => {
    username = usernameInput.value.trim();
    if (username) {
        connectWebSocket(username);
        chatArea.style.display = 'block';
        usernameInput.disabled = true;
        loginBtn.disabled = true;
    }
});

// Establish WebSocket connection
function connectWebSocket(user) {
    ws = new WebSocket('ws://localhost:8080');
    
    ws.onopen = () => {
        console.log('WebSocket connection established');
        ws.send(JSON.stringify({ type: 'login', username: user }));
    };

    ws.onmessage = (event) => {
        const message = JSON.parse(event.data);
        if (message.type === 'chat') {
            displayMessage(message.username, message.text);
        }
    };

    ws.onerror = (error) => {
        console.error('WebSocket error:', error);
    };

    ws.onclose = () => {
        console.log('WebSocket connection closed');
    };
}

// Display message in chat window
function displayMessage(user, message) {
    const li = document.createElement('li');
    li.textContent = `${user}: ${message}`;
    messageList.appendChild(li);
}

// Event listener for sending messages
sendBtn.addEventListener('click', () => {
    const message = messageInput.value.trim();
    if (message) {
        ws.send(JSON.stringify({ type: 'chat', text: message }));
        displayMessage(username, message);
        messageInput.value = '';
    }
});
</script>

</body>
</html>
```

### Server-Side (Node.js + WebSocket)

```javascript
// server.js
const WebSocket = require('ws');
const wss = new WebSocket.Server({ port: 8080 });

const users = [];

wss.on('connection', (ws) => {
    let currentUser = '';

    ws.on('message', (message) => {
        const data = JSON.parse(message);

        if (data.type === 'login') {
            currentUser = data.username;
            users.push(currentUser);
            console.log(`${currentUser} connected`);

            // Broadcast a message to all clients
            wss.clients.forEach(client => {
                if (client !== ws && client.readyState === WebSocket.OPEN) {
                    client.send(JSON.stringify({ type: 'chat', username: 'System', text: `${currentUser} has joined the chat!` }));
                }
            });
        } else if (data.type === 'chat') {
            // Broadcast chat message to all clients
            wss.clients.forEach(client => {
                if (client !== ws && client.readyState === WebSocket.OPEN) {
                    client.send(JSON.stringify({ type: 'chat', username: currentUser, text: data.text }));
                }
            });
        }
    });

    ws.on('close', () => {
        // Remove the user from the list of online users
        const index = users.indexOf(currentUser);
        if (index !== -1) {
            users.splice(index, 1);
            console.log(`${currentUser} disconnected`);
        }
    });
});

console.log('WebSocket server is running on ws://localhost:8080');
```

---

## 🧑‍💻 Key Concepts and Techniques Applied

- **WebSocket**: Learn how to create a persistent two-way communication channel for real-time interactions between the client and the server.
- **Event Handling**: Handle different types of WebSocket events such as `onopen`, `onmessage`, `onerror`, and `onclose`.
- **Message Broadcasting**: Send messages from the server to all connected clients in real time.
- **User Authentication**: Implement a basic username-based authentication system to identify users.
- **Real-time UI Updates**: Update the chat interface dynamically as messages are sent and received.

---

## ✅ Outcome

By the end of this project, you will have created a **Real-time Chat Application** using WebSockets, including the following:
- **User Authentication**: Users can log in with a username.
- **Real-time Messaging**: Messages are exchanged in real-time between all connected users.
- **Online User List**: The app shows a list of online users.
- **Responsive UI**: The chat application works seamlessly on both mobile and desktop devices.

---

## 📚 Resources

- [WebSocket API MDN](https://developer.mozilla.org/en-US/docs/Web/API/WebSocket)
- [Node.js WebSocket Library (`ws`)](https://www.npmjs.com/package/ws)

---

### Instructions:
- Set up a WebSocket server using Node.js and install the necessary dependencies (`ws`).

