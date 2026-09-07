# ChatAway 💬

A full-stack, real-time messaging application built with the **MERN stack** (MongoDB, Express.js, React.js, Node.js) and **Socket.IO**. Chat Away provides seamless bidirectional communication, supporting both private conversations and group chats with an emphasis on speed, security, and user experience.

---

## ⚡ Key Features

- **Real-Time Bidirectional Messaging:** Instant message delivery and broadcasting powered by Socket.IO.
- **Group Chat Management:** Create groups, add/remove users, and update group settings via dedicated modal interfaces (`GroupChatModal.js`, `UpdateGroupChatModal.js`).
- **Live Typing Indicators:** Visual typing feedback utilizing Lottie animations (`typing.json`) to enhance conversational presence.
- **Optimized Search & Performance:** Fast message retrieval and user search functionality, achieved through optimized Node.js services and MongoDB indexing on frequently queried collections.
- **Secure Authentication:** Robust user sessions and access-controlled routes secured by JSON Web Tokens (JWT) and encrypted data storage (`generateToken.js`, `authMiddleware.js`).
- **Global State Management:** Centralized frontend state handling using the React Context API (`ChatProvider.js`) for seamless data flow across components.

---

## 🏗️ Architecture & Tech Stack

- **Frontend:** React.js, React Context API, CSS (`App.css`, `index.css`)
- **Backend:** Node.js, Express.js
- **Database & ORM:** MongoDB, Mongoose (`db.js`)
- **Real-Time Communication:** Socket.IO
- **Authentication:** JWT (`generateToken.js`), bcrypt

---

## 🗂️ Project Structure

The repository is divided into independent frontend and backend workspaces:

```text
Chat-App-main/
├── backend/
│   ├── config/          # Database connection and JWT generation
│   ├── controllers/     # Route logic (chatControllers, messageControllers, userControllers)
│   ├── data/            # Static or seed data
│   ├── middleware/      # JWT verification and custom error handling
│   ├── models/          # Mongoose schemas (chatModel, messageModel, userModel)
│   ├── routes/          # Express API route definitions
│   └── server.js        # Entry point and Socket.IO initialization
└── frontend/
    ├── public/          # Static assets and index.html
    └── src/
        ├── animations/  # Lottie JSON files (e.g., typing.json)
        ├── components/  # Reusable UI, Chatbox, Modals, and Authentication forms
        ├── config/      # Chat logic and utility functions
        ├── Context/     # React Context providers (ChatProvider.js)
        └── Pages/       # Top-level views (Homepage.js, Chatpage.js)


## 🔌 API & Core Models Reference

The backend exposes a RESTful API to manage the core application state, interfacing with three primary MongoDB models:

### Models
*   **`userModel.js`:** Manages user profiles, credentials, and authentication state.
*   **`chatModel.js`:** Defines chat entities, distinguishing between one-on-one conversations and group chats, and tracks participating users.
*   **`messageModel.js`:** Stores individual message payloads, linking them to a specific sender and a parent chat document.

### Key API Routes
*   **`/api/user`:** Handles user registration, login (JWT generation), and user search queries (`userRoutes.js`).
*   **`/api/chat`:** Manages creating new chats, fetching chat history, and group administration (`chatRoutes.js`).
*   **`/api/message`:** Handles sending new messages and retrieving message pagination for specific chats (`messageRoutes.js`).

---

## 🚀 Getting Started

### Prerequisites
- **Node.js:** `>= 14.x`
- **MongoDB:** Local instance or MongoDB Atlas URI

### 1. Clone the Repository
```bash
git clone [https://github.com/akshitgarg08/Chat-App.git](https://github.com/akshitgarg08/Chat-App.git)
cd Chat-App-main
```

### 2. Backend Setup
```bash
cd backend
npm install
```
Create a `.env` file in the `backend` directory:
```env
PORT=5000
MONGO_URI=your_mongodb_connection_string
JWT_SECRET=your_super_secret_jwt_key
```
Start the backend server:
```bash
npm start
```

### 3. Frontend Setup
Open a new terminal window:
```bash
cd frontend
npm install
```
Start the React development server:
```bash
npm start
```

Open [http://localhost:3000](http://localhost:3000) in your browser to start chatting.
