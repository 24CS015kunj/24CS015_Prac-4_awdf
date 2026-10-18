# Task Manager API (Practical-4)

A RESTful API built with **Node.js** and **Express.js** for managing tasks. It demonstrates custom middleware (request logging and global error handling) and full CRUD operations on task resources.

---

## 🚀 Features

- **CRUD Operations**: Create, Read, Update, and Delete tasks.
- **Custom Logging Middleware**: Logs incoming request methods, URLs, and timestamps.
- **Global Error Handling**: Catches and formats internal server errors cleanly.
- **Fallback 404 Handler**: Returns standardized JSON responses for undefined routes.
- **Flexible Endpoints**: Routes configured for both `/tasks` and `/taskes`.

---

## 📁 Project Structure

```text
AWDF-Practical-4/
├── middleware/
│   ├── errorHandler.js   # Global error handling middleware
│   └── logger.js         # Request logging middleware
├── routes/
│   └── taskRoutes.js     # Task CRUD route handlers
├── app.js                # Application entry point & server config
├── package.json          # Project dependencies and npm scripts
└── README.md             # Project documentation
```

---

## 🛠️ Prerequisites & Installation

1. **Node.js** (v14 or higher recommended)
2. Open terminal in the project directory:

```bash
cd AWDF-Practical-4
```

3. Install project dependencies:

```bash
npm install
```

---

## 🏃 Running the Application

### Development Mode (with hot-reload using Nodemon):
```bash
npm run dev
```

### Production / Standard Mode:
```bash
npm start
```

The server will start at:
```text
http://localhost:5000
```

---

## 📡 API Endpoints

Base URL: `http://localhost:5000/tasks` (also accessible via `/taskes`)

| Method | Endpoint | Description | Request Body Example | Success Status |
| :--- | :--- | :--- | :--- | :--- |
| **GET** | `/tasks` | Get all tasks | None | `200 OK` |
| **POST** | `/tasks` | Create a new task | `{"title": "Complete assignment", "completed": false}` | `201 Created` |
| **PUT** | `/tasks/:id` | Update an existing task | `{"title": "Updated Task", "completed": true}` | `200 OK` |
| **DELETE**| `/tasks/:id` | Delete a task by ID | None | `200 OK` |

---

## 🧪 Example API Requests (curl / Postman)

### 1. Get All Tasks
```bash
curl -X GET http://localhost:5000/tasks
```

### 2. Create a Task
```bash
curl -X POST http://localhost:5000/tasks \
  -H "Content-Type: application/json" \
  -d "{\"title\": \"Build REST API\", \"completed\": false}"
```

### 3. Update a Task
```bash
curl -X PUT http://localhost:5000/tasks/1 \
  -H "Content-Type: application/json" \
  -d "{\"title\": \"Learn Node.js & Express\", \"completed\": true}"
```

### 4. Delete a Task
```bash
curl -X DELETE http://localhost:5000/tasks/1
```
