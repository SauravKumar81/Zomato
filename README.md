# 🥗 Zomato Clone – Full Stack App

This is a **Zomato Clone** built using the **MERN stack (MongoDB, Express.js, React, Node.js)**.  
It includes both the backend (API server) and frontend (React web app) for food delivery and management.

---

## 🚀 Features

### Backend (Node.js + Express)
- 🔐 User Authentication (Register, Login, Logout)
- 🍔 Food Item CRUD operations
- 🧑‍🍳 Food Partner Management
- 🍪 Cookie-based Authentication with JWT
- 🌐 CORS-enabled for React frontend

### Frontend (React)
- 🧭 Navigation using React Router
- 👤 User & Partner login/registration pages
- 🏠 Home and Saved pages with bottom navigation
- 🍱 Food creation and partner profile pages
- 🪄 Responsive design with clean UI

---

## 🧰 Tech Stack

| Layer | Technology |
|--------|-------------|
| **Frontend** | React, React Router, Axios |
| **Backend** | Node.js, Express.js |
| **Database** | MongoDB (Mongoose) |
| **Authentication** | JWT + Cookies |
| **Others** | CORS, dotenv, cookie-parser |

---

## 📁 Folder Structure

```
Zomato/
│
├── backend/
│   ├── routes/
│   ├── controllers/
│   ├── models/
│   ├── app.js
│   ├── server.js
│   ├── .env
│   └── package.json
│
└── frontend/
    ├── src/
    │   ├── pages/
    │   │   ├── auth/
    │   │   ├── food-partner/
    │   │   └── general/
    │   ├── components/
    │   ├── AppRoutes.jsx
    │   └── main.jsx
    ├── public/
    ├── package.json
    └── vite.config.js
```

---

## ⚙️ Backend Setup

### 1. Navigate to backend folder
```bash
cd backend
```

### 2. Install dependencies
```bash
npm install
```

### 3. Create `.env` file
```env
PORT=3000
MONGO_URI=your_mongodb_connection_string
JWT_SECRET=your_secret_key
```

### 4. Run backend
```bash
npm start
```
Server will start at **http://localhost:3000**

---

## 💻 Frontend Setup

### 1. Navigate to frontend folder
```bash
cd frontend
```

### 2. Install dependencies
```bash
npm install
```

### 3. Start frontend (Vite)
```bash
npm run dev
```

Frontend will start at **http://localhost:5173**

---

## 🧭 React Router Setup (src/AppRoutes.jsx)

```jsx
import React from 'react'
import { BrowserRouter as Router, Route, Routes } from 'react-router-dom';
import UserRegister from '../pages/auth/UserRegister';
import ChooseRegister from '../pages/auth/ChooseRegister';
import UserLogin from '../pages/auth/UserLogin';
import FoodPartnerRegister from '../pages/auth/FoodPartnerRegister';
import FoodPartnerLogin from '../pages/auth/FoodPartnerLogin';
import Home from '../pages/general/Home';
import Saved from '../pages/general/Saved';
import BottomNav from '../components/BottomNav';
import CreateFood from '../pages/food-partner/CreateFood';
import Profile from '../pages/food-partner/Profile';

const AppRoutes = () => {
    return (
        <Router>
            <Routes>
                <Route path="/register" element={<ChooseRegister />} />
                <Route path="/user/register" element={<UserRegister />} />
                <Route path="/user/login" element={<UserLogin />} />
                <Route path="/food-partner/register" element={<FoodPartnerRegister />} />
                <Route path="/food-partner/login" element={<FoodPartnerLogin />} />
                <Route path="/" element={<><Home /><BottomNav /></>} />
                <Route path="/saved" element={<><Saved /><BottomNav /></>} />
                <Route path="/create-food" element={<CreateFood />} />
                <Route path="/food-partner/:id" element={<Profile />} />
            </Routes>
        </Router>
    )
}

export default AppRoutes;
```

---

## 🌍 CORS Setup
Your backend is configured to accept frontend requests from:
```
http://localhost:5173
```

---

## 🧪 API Testing
Use **Postman** or **Thunder Client** in VS Code to test:
```
POST http://localhost:3000/api/auth/login
```

---

## 📜 License
This project is open-source and available under the **MIT License**.