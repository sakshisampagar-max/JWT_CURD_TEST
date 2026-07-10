# JWT Authentication + CRUD Notes App

A beginner-friendly full-stack Notes application built with **React**, **Express.js**, **MongoDB Atlas**, **JWT Authentication**, and **bcrypt.js**.

Users can:

- Register a new account
- Login securely using JWT
- Create notes
- View their own notes
- Edit notes
- Delete notes
- Logout

Each user can access **only their own notes**.

---

# Technologies Used

## Frontend

- React
- React Hooks
- Fetch API
- CSS

## Backend

- Node.js
- Express.js
- MongoDB Atlas
- Mongoose
- JWT (jsonwebtoken)
- bcryptjs
- dotenv
- cors

---

# Project Structure

```
project-folder/
│
├── backend/
│   ├── server.js
│   ├── .env
│   ├── package.json
│
├── frontend/
│   ├── src/
│   │    ├── App.jsx
│   │    ├── App.css
│   │    └── main.jsx
│   │
│   ├── assets/
│   │    ├── login.png
│   │    ├── register.png
│   │    ├── dashboard.png
│   │    └── edit-note.png
│   │
│   └── package.json
│
└── README.md
```

---

# Features

- JWT Authentication
- Password Hashing using bcrypt
- Protected Routes
- User Registration
- User Login
- Secure Logout
- Create Notes
- Read Notes
- Update Notes
- Delete Notes
- MongoDB Atlas Database
- Responsive UI
- Beginner Friendly Code

---

# Database Collections

## Users

| Field | Type |
|--------|------|
| username | String |
| password | Hashed String |

---

## Notes

| Field | Type |
|--------|------|
| username | String |
| text | String |
| createdAt | Date |
| updatedAt | Date |

---

# API Endpoints

## Register

```
POST /register
```

Body

```json
{
    "username":"john",
    "password":"123456"
}
```

---

## Login

```
POST /login
```

Body

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

## Create Note

```
POST /notes
```

Header

```
Authorization: Bearer YOUR_TOKEN
```

Body

```json
{
    "text":"My first note"
}
```

---

## Get Notes

```
GET /notes
```

Header

```
Authorization: Bearer YOUR_TOKEN
```

---

## Update Note

```
PUT /notes/:id
```

Header

```
Authorization: Bearer YOUR_TOKEN
```

Body

```json
{
    "text":"Updated note"
}
```

---

## Delete Note

```
DELETE /notes/:id
```

Header

```
Authorization: Bearer YOUR_TOKEN
```

---

# Installation

## 1. Clone Repository

```bash
git clone https://github.com/your-username/jwt-notes-app.git
```

---

## 2. Backend Setup

Move into backend

```bash
cd backend
```

Install dependencies

```bash
npm install
```

Create a `.env`

```env
PORT=5000

MONGO_URI=YOUR_MONGODB_ATLAS_CONNECTION_STRING

JWT_SECRET=your-secret-key
```

Run backend

```bash
node server.js
```

or

```bash
npm start
```

---

## 3. Frontend Setup

Move into frontend

```bash
cd frontend
```

Install dependencies

```bash
npm install
```

Run

```bash
npm run dev
```

---

# Screenshots

Place the screenshots inside the **frontend/assets/** folder (or an `assets/` folder at the project root) using the following filenames.

## Login Page

```
assets/login.png
```

Markdown:

```markdown
### Login Page

![Login](assets/login.png)
```

---

## Register Page

```
assets/register.png
```

Markdown:

```markdown
### Register Page

![Register](assets/register.png)
```

---

## Dashboard

```
assets/dashboard.png
```

Markdown:

```markdown
### Dashboard

![Dashboard](assets/dashboard.png)
```

---

## Edit Note

```
assets/edit-note.png
```

Markdown:

```markdown
### Edit Note

![Edit Note](assets/edit-note.png)
```

---

# Example README Screenshot Section

```markdown
# Screenshots

## Login

![Login](assets/login.png)

---

## Register

![Register](assets/register.png)

---

## Dashboard

![Dashboard](assets/dashboard.png)

---

## Edit Note

![Edit Note](assets/edit-note.png)
```

---

# Authentication Flow

```
Register
      │
      ▼
Password Hashing (bcrypt)
      │
      ▼
Save User to MongoDB
      │
      ▼
Login
      │
      ▼
Verify Password
      │
      ▼
Generate JWT Token
      │
      ▼
React Stores Token
      │
      ▼
Send Token in Authorization Header
      │
      ▼
Protected Express Routes
      │
      ▼
CRUD Operations
```

---

# Security Features

- Passwords are hashed using bcrypt.
- JWT protects all CRUD endpoints.
- Users can access only their own notes.
- JWT expires after one hour.
- Sensitive configuration is stored in a `.env` file.

---

# Future Improvements

- Persist JWT using Local Storage.
- Refresh Tokens.
- User Profile Page.
- Search Notes.
- Pagination.
- Categories.
- Rich Text Editor.
- Dark Mode.
- File Uploads.
- Note Sharing.
- Email Verification.
- Forgot Password.

---

# Author

**Sakshi Sampagar**

---

# License

This project is intended for learning and educational purposes.
