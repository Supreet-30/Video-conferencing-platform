# Video Conferencing Platform

A modern, real-time video conferencing application built with the **MERN Stack** (MongoDB, Express, React, Node.js). Connect, communicate, and collaborate seamlessly with high-quality video and audio streaming using WebSocket technology.

---

## 🎯 Overview

This platform enables users to initiate or join video conferences with multiple participants. With real-time socket communication, secure authentication, and an intuitive user interface, it provides a complete solution for remote meetings and collaboration.

---

## ✨ Features

- **Real-Time Video Conferencing** - High-quality peer-to-peer video and audio communication
- **User Authentication** - Secure login and registration with password hashing
- **Meeting Rooms** - Create and join meeting rooms using unique URLs
- **Meeting History** - Track and access previous meeting sessions
- **Responsive Design** - Seamless experience across desktop and mobile devices
- **WebSocket Communication** - Instant, bidirectional communication using Socket.IO
- **User Session Management** - Persistent user sessions and authentication tokens

---

## 🏗️ Tech Stack

### Frontend
- **React 18** - Modern UI library with hooks and functional components
- **React Router v6** - Client-side navigation and routing
- **Material-UI (MUI)** - Professional UI component library
- **Axios** - HTTP client for API requests
- **Socket.IO Client** - Real-time WebSocket communication

### Backend
- **Node.js with Express** - Lightweight web server framework
- **Socket.IO** - WebSocket library for real-time bidirectional communication
- **MongoDB with Mongoose** - NoSQL database and ODM
- **Bcrypt** - Password hashing and security
- **CORS** - Cross-origin resource sharing

### Language Composition
- **JavaScript** - 90.8%
- **CSS** - 5.7%
- **HTML** - 3.5%

---

## 📋 Prerequisites

Before getting started, ensure you have:
- **Node.js** (v14 or higher)
- **npm** (v6 or higher)
- **MongoDB** (local or MongoDB Atlas connection)
- **Git**

---

## 🚀 Getting Started

### 1. Clone the Repository
```bash
git clone https://github.com/Supreet-30/Video-conferencing-platform.git
cd Video-conferencing-platform
```

### 2. Backend Setup

Navigate to the backend directory:
```bash
cd backend
npm install
```

Create a `.env` file in the backend directory with your configuration:
```env
PORT=8000
MONGODB_URI=mongodb+srv://<username>:<password>@cluster0.xxxxx.mongodb.net/
NODE_ENV=development
```

Start the backend server:
```bash
# Development mode with auto-reload
npm run dev

# Production mode
npm start
```

The backend will run on `http://localhost:8000`

### 3. Frontend Setup

In a new terminal, navigate to the frontend directory:
```bash
cd frontend
npm install
```

Start the React development server:
```bash
npm start
```

The application will open at `http://localhost:3000`

---

## 📁 Project Structure

```
Video-conferencing-platform/
├── backend/
│   ├── src/
│   │   ├── app.js                 # Express app setup & Socket.IO initialization
│   │   ├── controllers/
│   │   │   └── socketManager.js   # WebSocket event handling
│   │   ├── routes/
│   │   │   └── users.routes.js    # User API endpoints
│   │   └── models/                # MongoDB schemas
│   ├── package.json
│   └── README.md
├── frontend/
│   ├── src/
│   │   ├── App.js                 # Main app component with routing
│   │   ├── pages/
│   │   │   ├── landing.js         # Landing page
│   │   │   ├── authentication.js  # Auth/login page
│   │   │   ├── home.js            # Home dashboard
│   │   │   ├── VideoMeet.js       # Video conferencing component
│   │   │   └── history.js         # Meeting history
│   │   ├── contexts/
│   │   │   └── AuthContext.js     # Authentication context
│   │   ├── App.css
│   │   └── index.js
│   ├── package.json
│   └── README.md
└── README.md
```

---

## 🔧 Backend Architecture

### Socket Events
The backend uses Socket.IO for real-time communication:

```javascript
// Socket.IO initialization in app.js
import { createServer } from "node:http";
import { Server } from "socket.io";

const server = createServer(app);
const io = connectToSocket(server);
```

### Database Connection
MongoDB is used for storing user data and meeting history:

```javascript
const connectionDb = await mongoose.connect(
  "mongodb+srv://<username>:<password>@cluster0.xxxxx.mongodb.net/"
);
```

### API Routes
User authentication and meeting endpoints are available at:
- `GET/POST /api/v1/users` - User management endpoints

---

## 💻 Frontend Architecture

### Routing
React Router manages navigation between pages:

```javascript
<Routes>
  <Route path='/' element={<LandingPage />} />
  <Route path='/auth' element={<Authentication />} />
  <Route path='/home' element={<HomeComponent />} />
  <Route path='/history' element={<History />} />
  <Route path='/:url' element={<VideoMeetComponent />} />
</Routes>
```

### Authentication Context
Global state management for user authentication:

```javascript
<AuthProvider>
  {/* All routes have access to auth context */}
</AuthProvider>
```

### Video Meeting Component
The main video conferencing interface handles:
- Video/audio stream capture
- Peer connection management
- Real-time communication via Socket.IO

---

## 🛠️ Available Scripts

### Backend
```bash
npm run dev    # Development with nodemon (auto-reload)
npm start      # Production mode
npm run prod   # Production with PM2
```

### Frontend
```bash
npm start      # Start development server
npm run build  # Build for production
npm test       # Run tests
npm run eject  # Eject from Create React App (irreversible)
```

---

## 🔐 Security Features

- **Password Hashing** - Bcrypt for secure password storage
- **CORS Protection** - Configured CORS for API requests
- **Authentication** - Token-based user authentication
- **Input Validation** - Request payload size limits (40kb)

---

## 📞 How to Use

1. **Access the Platform** - Open `http://localhost:3000` in your browser
2. **Create an Account** - Sign up with your email and password on the authentication page
3. **Create a Meeting** - From the home dashboard, create a new video conference room
4. **Share the Link** - Share the unique meeting URL with participants
5. **Join a Meeting** - Participants can join using the shared URL
6. **View History** - Access your meeting history from the history page

---

## 🐛 Troubleshooting

### Backend won't start
- Ensure MongoDB connection string is correct in `.env`
- Check if port 8000 is not already in use
- Verify Node.js and npm versions

### Frontend connection issues
- Make sure backend is running on port 8000
- Clear browser cache and restart development server
- Check browser console for Socket.IO connection errors

### Video not streaming
- Allow camera and microphone permissions in browser
- Ensure both participants are on stable internet connections
- Check firewall settings for Socket.IO WebSocket access

---

## 📚 Dependencies

### Backend Dependencies
- `express` - Web framework
- `socket.io` - Real-time communication
- `mongoose` - MongoDB ODM
- `bcrypt` - Password security
- `cors` - Cross-origin handling
- `nodemon` - Development auto-reload

### Frontend Dependencies
- `react` - UI framework
- `react-router-dom` - Routing
- `@mui/material` - UI components
- `axios` - HTTP requests
- `socket.io-client` - WebSocket client

---
