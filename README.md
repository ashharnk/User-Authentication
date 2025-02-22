# User Authentication and Authorization with Bearer Token

This project is a **Node.js** application using **Express.js**, **Mongoose**, and **JWT** for user authentication and authorization with **Bearer tokens**. It follows the **MVC pattern** and includes **API documentation**.

---

## 🚀 Features
- User Registration with hashed passwords
- User Login with JWT token generation
- Protected routes with JWT verification middleware
- MongoDB Atlas integration
- Clean, well-documented code with error handling

---

## 🗂️ Project Structure
```
├── models
│   └── User.js        # User schema with Mongoose
├── controllers
│   └── authController.js  # Handles registration and login logic
├── middleware
│   └── authMiddleware.js  # JWT token verification
├── routes
│   └── authRoutes.js      # API routes for authentication
├── .env                   # Environment variables
├── server.js              # Main server file
└── README.md              # Project documentation
```

---

## 🛠️ Setup & Installation
1. **Clone the repository:**
   ```bash
   git clone https://github.com/your-username/your-repo.git
   cd your-repo
   ```

2. **Install dependencies:**
   ```bash
   npm install
   ```

3. **Create a `.env` file:**
   ```env
   PORT=5000
   MONGO_URI=your_mongodb_atlas_connection_string
   JWT_SECRET=your_secure_jwt_secret
   ```

4. **Run the server:**
   ```bash
   npm start
   ```

---

## 📮 API Endpoints

### **1. Register User**
- **URL:** `/api/register`  
- **Method:** POST  
- **Payload:**
  ```json
  {
    "username": "john_doe",
    "email": "john@example.com",
    "password": "securePassword123"
  }
  ```
- **Success Response:**
  ```json
  {
    "message": "User registered successfully"
  }
  ```

---

### **2. Login User**
- **URL:** `/api/login`  
- **Method:** POST  
- **Payload:**
  ```json
  {
    "email": "john@example.com",
    "password": "securePassword123"
  }
  ```
- **Success Response:**
  ```json
  {
    "token": "Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9..."
  }
  ```

---

### **3. Get User Info (Protected)**
- **URL:** `/api/user`  
- **Method:** GET  
- **Headers:**
  ```json
  {
    "Authorization": "Bearer <your_token>"
  }
  ```
- **Success Response:**
  ```json
  {
    "_id": "65d6fbd2e9e5b8f9c3a9a234",
    "username": "john_doe",
    "email": "john@example.com"
  }
  ```

---

## 🔒 JWT Token Payload
```json
{
  "id": "65d6fbd2e9e5b8f9c3a9a234",
  "email": "john@example.com",
  "iat": 1708588800,
  "exp": 1708592400
}
```

---

## 📝 Sample `.env` File
```env
PORT=5000
MONGO_URI=your_mongodb_atlas_connection_string
JWT_SECRET=6c4a1e2bde95f417c3eafc0b2a8f70bd1d92be8a8b25f0e4fcf748abc02c19ab92345678ffab12cfaed981a3b674ef9
```

---

## 🧪 Testing with Postman
1. **Import the Postman collection** (provided in the `docs` folder or create your own).
2. **Test the following workflows:**
   - Register a new user.
   - Login and retrieve the JWT token.
   - Access protected routes using the token.

---
