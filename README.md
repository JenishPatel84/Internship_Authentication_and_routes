# JWT Authentication & Protected Routes

## Overview

This project demonstrates a complete authentication system using JWT (JSON Web Tokens), bcrypt password hashing, and protected routes. Users can register, log in, and access protected resources only after successful authentication.

## Features

* User Registration
* User Login
* Password Hashing with bcrypt
* JWT Token Generation
* Protected API Routes
* Protected React Pages
* Authentication Middleware
* Logout Functionality

## Tech Stack

### Backend

* Node.js
* Express.js
* MongoDB
* Mongoose
* bcrypt
* jsonwebtoken

### Frontend

* React.js
* React Router
* Axios

## Project Structure

backend/
├── controllers/
├── middleware/
├── models/
├── routes/
├── server.js

frontend/
├── src/
│ ├── pages/
│ ├── components/
│ ├── routes/
│ └── App.js

## Installation

### Clone Repository

git clone <repository-url>

### Backend Setup

cd backend
npm install

Create a .env file:

PORT=5000
MONGO_URI=your_mongodb_connection_string
JWT_SECRET=your_secret_key

Run backend:
npm start

### Frontend Setup

cd frontend
npm install
npm start

## API Endpoints

### Register User

POST /api/auth/register

Request:
{
"name": "John",
"email": "[john@example.com](mailto:john@example.com)",
"password": "password123"
}

### Login User

POST /api/auth/login

Request:
{
"email": "[john@example.com](mailto:john@example.com)",
"password": "password123"
}

Response:
{
"token": "jwt_token"
}

### Protected Route

GET /api/user/profile

Headers:
Authorization: Bearer <token>

## Authentication Flow

1. User registers an account.
2. Password is hashed using bcrypt before storing.
3. User logs in with email and password.
4. Server verifies credentials.
5. JWT token is generated and returned.
6. Client stores token.
7. Token is sent with protected requests.
8. Middleware verifies JWT before granting access.

## Security Notes

### Password Storage

* Passwords are hashed using bcrypt.
* Plain-text passwords are never stored.

### Token Storage

Recommended:

* HttpOnly Cookies

Alternative:

* localStorage (less secure)

### Common Pitfalls

* Never expose JWT_SECRET.
* Always validate user input.
* Use HTTPS in production.
* Set token expiration times.
* Implement proper error handling.

## Future Improvements

* Refresh Tokens
* Email Verification
* Password Reset
* Role-Based Access Control (RBAC)

## Author

Your Name
