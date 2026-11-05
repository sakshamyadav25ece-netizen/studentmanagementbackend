# Student Management / Backend Web Development API

A modular, production-ready backend built with **Node.js**, **Express.js**, and **MongoDB (Mongoose)** implementing the Model-Route-Controller (MRC) architectural pattern, secure user authentication with password hashing (`bcrypt`), and complete CRUD operations.

---

## 🚀 Features

- **Architecture:** Clean Model-Route-Controller (MRC) pattern using modern ES Modules.
- **Database:** MongoDB Atlas integration using Mongoose ORM.
- **Security:** Secure password hashing using `bcrypt` pre-save hooks and constant-time password comparison.
- **User Authentication:** Registration, login, and session/logout handling.
- **CRUD Operations:** Complete Create, Read, Update, and Delete APIs for resource management.
- **Environment Management:** Centralized configuration via `dotenv`.

---

## 📁 Project Structure

```text
├── backend/
│   └── src/
│       ├── config/
│       │   ├── constants.js          # App constants (DB_NAME, etc.)
│       │   └── database.js           # MongoDB connection handler
│       ├── controllers/
│       │   ├── post.controller.js    # CRUD business logic (create, read, update, delete)
│       │   └── user.controller.js    # Auth business logic (register, login, logout)
│       ├── models/
│       │   ├── post.model.js         # Post schema definition (name, description, age)
│       │   └── user.model.js         # User schema with bcrypt password hashing
│       ├── routes/
│       │   ├── post.route.js         # Post route definitions
│       │   └── user.route.js         # User authentication route definitions
│       ├── app.js                    # Express app initialization & route mounting
│       └── index.js                  # Application entry point & server listener
├── .env.example                      # Template for environment variables
├── .gitignore                        # Git ignore file
├── package.json                      # Project metadata & dependencies
└── README.md                         # Project documentation
```

---

## 🛠️ Tech Stack & Dependencies

- **Runtime:** Node.js (v18+)
- **Framework:** Express.js (`^5.1.0`)
- **Database:** MongoDB Atlas via Mongoose (`^8.18.3`)
- **Authentication / Encryption:** `bcrypt` (`^6.0.0`)
- **Environment Management:** `dotenv` (`^17.2.2`)
- **Development Tool:** `nodemon` (`^3.1.10`)

---

## 📡 API Endpoints

### 1. User Authentication (`/api/v1/users`)

| Method | Endpoint | Description | Request Body |
|--------|----------|-------------|--------------|
| `POST` | `/api/v1/users/register` | Register a new user | `{ "username": "...", "email": "...", "password": "..." }` |
| `POST` | `/api/v1/users/login` | Log in an existing user | `{ "email": "...", "password": "..." }` |
| `POST` | `/api/v1/users/logout` | Log out a user | `{ "email": "..." }` |

### 2. Posts CRUD Operations (`/api/v1/posts`)

| Method | Endpoint | Description | Request Body / Params |
|--------|----------|-------------|-----------------------|
| `POST` | `/api/v1/posts/create` | Create a new post | `{ "name": "...", "description": "...", "age": 20 }` |
| `GET` | `/api/v1/posts/getPosts` | Fetch all posts | None |
| `PATCH` | `/api/v1/posts/update/:id` | Update an existing post by ID | `{ "description": "...", "name": "..." }` |
| `DELETE` | `/api/v1/posts/delete/:id` | Delete a post by ID | URL parameter `:id` |

---

## ⚙️ Installation & Setup

### 1. Clone the repository
```bash
git clone https://github.com/sakshamyadav25ece-netizen/studentmanagementbackend.git
cd studentmanagementbackend
```

### 2. Install dependencies
```bash
npm install
```

### 3. Configure environment variables
Create a `.env` file in the root directory (based on `.env.example`):
```env
PORT=4000
MONGODB_URI="your_mongodb_connection_string"
```

### 4. Start the development server
```bash
npm run dev
```
The server will start listening at `http://localhost:4000`.
