# JWT Authentication & Notes CRUD Application

A full-stack Notes application built with **React.js**, **Node.js**, **Express.js**, **MongoDB Atlas**, **JWT Authentication**, and **Bcrypt**.

Users can register, log in securely, and perform complete CRUD (Create, Read, Update, Delete) operations on their own notes.

---

# Features

- User Registration
- Secure Login using JWT
- Password Hashing using Bcrypt
- Protected API Routes
- Create Notes
- View Notes
- Edit Notes
- Delete Notes
- MongoDB Atlas Database
- Responsive React Frontend
- REST API Architecture

---

# Technology Stack

### Frontend

- React.js
- CSS3
- Fetch API

### Backend

- Node.js
- Express.js
- JWT (jsonwebtoken)
- bcryptjs
- dotenv
- cors

### Database

- MongoDB Atlas
- Mongoose

---

# Project Structure

```
jwt-notes-app/
│
├── client/
│   ├── public/
│   ├── src/
│   │    ├── App.jsx
│   │    ├── App.css
│   │    └── main.jsx
│   └── package.json
│
├── server/
│   ├── server.js
│   ├── .env
│   └── package.json
│
├── assets/
│   ├── login.png
│   ├── register.png
│   ├── dashboard.png
│   ├── add-note.png
│   ├── edit-note.png
│   └── delete-note.png
│
└── README.md
```

---

# Installation

## 1. Clone Repository

```bash
git clone https://github.com/yourusername/jwt-notes-app.git

cd jwt-notes-app
```

---

## 2. Install Frontend

```bash
cd client

npm install
```

---

## 3. Install Backend

```bash
cd ../server

npm install
```

---

# Environment Variables

Create a `.env` file inside the **server** folder.

```env
PORT=5000

JWT_SECRET=your_secret_key

MONGO_URI=mongodb+srv://username:password@cluster.mongodb.net/jwtcrud
```

---

# Running the Project

### Start Backend

```bash
cd server

npm start
```

Server runs on

```
http://localhost:5000
```

---

### Start Frontend

```bash
cd client

npm run dev
```

Open

```
http://localhost:5173
```

---

# REST API Endpoints

## Authentication

### Register

```
POST /register
```

Request

```json
{
    "username":"john",
    "password":"123456"
}
```

---

### Login

```
POST /login
```

Request

```json
{
    "username":"john",
    "password":"123456"
}
```

Response

```json
{
    "token":"JWT_TOKEN"
}
```

---

## Notes

### Get All Notes

```
GET /notes
```

Authorization

```
Bearer TOKEN
```

---

### Create Note

```
POST /notes
```

```json
{
    "text":"My first note"
}
```

---

### Update Note

```
PUT /notes/:id
```

```json
{
    "text":"Updated Note"
}
```

---

### Delete Note

```
DELETE /notes/:id
```

---

# JWT Authentication Flow

```
User
   │
   │ Register
   ▼
Database

   │
   │ Login
   ▼

Server

   │
   │ Verify Password
   ▼

Generate JWT

   │
   ▼

Frontend stores Token

   │
   ▼

Every Protected Request

Authorization:
Bearer JWT_TOKEN

   │
   ▼

Server verifies JWT

   │
   ▼

Allow CRUD Operations
```

---

# Application Workflow

1. Register a new account.
2. Login using registered credentials.
3. Server generates a JWT token.
4. React stores the token in state.
5. Every request includes the token.
6. Backend verifies the JWT.
7. Authenticated users can manage only their own notes.

---

# Password Security

Passwords are never stored in plain text.

Example

```
123456

↓

$2a$10$E7dH...
```

The application uses:

- bcrypt.hash()
- bcrypt.compare()

---

# Screenshots

## Login Page

```
assets/login.png
```

![Login](Login.png)

---

## Registration Page

```
assets/register.png
```

![Register](demo.png)

---


## Add Note

```
assets/add-note.png
```

![Add Note](Add note.png)

---

# Future Improvements

- Refresh Tokens
- Remember Me Login
- User Profile
- Dark Mode
- Categories
- Search Notes
- Pagination
- Rich Text Editor
- File Upload
- Note Sharing
- Password Reset
- Email Verification
- Docker Deployment

---

# Dependencies

Frontend

```
react
```

Backend

```
express
mongoose
jsonwebtoken
bcryptjs
cors
dotenv
```

---

# Author

**Your Name**

BCA Full Stack Development Project

---

# License

This project is developed for educational purposes.
