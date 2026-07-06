# 📡 API Documentation

## Base URL
```
http://localhost:3000/api
```

## Authentication

Todos os endpoints (exceto auth) requerem o header:
```
Authorization: Bearer <jwt_token>
```

---

## 🔐 Authentication Endpoints

### Register
```
POST /auth/register

Body:
{
  "email": "user@example.com",
  "password": "password123",
  "name": "John Doe"
}

Response (201):
{
  "id": "uuid",
  "email": "user@example.com",
  "name": "John Doe",
  "token": "jwt_token"
}
```

### Login
```
POST /auth/login

Body:
{
  "email": "user@example.com",
  "password": "password123"
}

Response (200):
{
  "id": "uuid",
  "email": "user@example.com",
  "name": "John Doe",
  "token": "jwt_token"
}
```

### Refresh Token
```
POST /auth/refresh

Response (200):
{
  "token": "new_jwt_token"
}
```

---

## 📝 Task Endpoints

### List All Tasks
```
GET /tasks?quadrant=1&status=pending&priority=high

Query Parameters (optional):
- quadrant: 1-4 | null (backlog)
- status: pending | completed | cancelled
- priority: low | medium | high

Response (200):
[
  {
    "id": "uuid",
    "title": "Task Title",
    "description": "Task Description",
    "quadrant": 1,
    "priority": "high",
    "status": "pending",
    "dueDate": "2024-12-31T23:59:59Z",
    "category": "Work",
    "tags": ["urgent", "important"],
    "createdAt": "2024-01-01T00:00:00Z",
    "updatedAt": "2024-01-01T00:00:00Z"
  }
]
```

### Get Task by ID
```
GET /tasks/:id

Response (200):
{
  "id": "uuid",
  "title": "Task Title",
  ...
}
```

### Create Task
```
POST /tasks

Body:
{
  "title": "New Task",
  "description": "Task description",
  "priority": "high",
  "category": "Work",
  "dueDate": "2024-12-31T23:59:59Z",
  "tags": ["urgent"]
}

Response (201):
{
  "id": "uuid",
  "quadrant": null,
  ...
}
```

### Update Task
```
PUT /tasks/:id

Body:
{
  "title": "Updated Title",
  "description": "Updated description",
  "priority": "medium",
  ...
}

Response (200):
{ task object }
```

### Move Task to Quadrant
```
PATCH /tasks/:id/quadrant

Body:
{
  "quadrant": 1,
  "position": 0
}

Response (200):
{ task object }
```

### Update Task Status
```
PATCH /tasks/:id/status

Body:
{
  "status": "completed"
}

Response (200):
{ task object }
```

### Delete Task
```
DELETE /tasks/:id

Response (204): No Content
```

---

## 🗂️ Backlog Endpoints

### Get Backlog
```
GET /backlog

Response (200):
[
  { task object }
]
```

### Create Task in Backlog
```
POST /backlog

Body:
{
  "title": "Backlog Task",
  "description": "Description",
  ...
}

Response (201):
{ task object with quadrant: null }
```

---

## 📊 Dashboard Endpoints

### Get Dashboard Stats
```
GET /dashboard/stats

Response (200):
{
  "totalTasks": 10,
  "completedTasks": 3,
  "pendingTasks": 7,
  "backlogTasks": 2,
  "tasksByQuadrant": {
    "q1": 2,
    "q2": 3,
    "q3": 2,
    "q4": 1
  },
  "tasksByPriority": {
    "high": 3,
    "medium": 5,
    "low": 2
  }
}
```

### Get Tasks by Quadrant
```
GET /dashboard/by-quadrant

Response (200):
{
  "q1": [{ task objects }],
  "q2": [{ task objects }],
  "q3": [{ task objects }],
  "q4": [{ task objects }]
}
```

### Get Tasks by Priority
```
GET /dashboard/by-priority

Response (200):
{
  "high": 3,
  "medium": 5,
  "low": 2
}
```

---

## 🏷️ Category Endpoints

### List Categories
```
GET /categories

Response (200):
[
  {
    "id": "uuid",
    "name": "Work",
    "color": "#FF0000",
    "createdAt": "2024-01-01T00:00:00Z"
  }
]
```

### Create Category
```
POST /categories

Body:
{
  "name": "Personal",
  "color": "#00FF00"
}

Response (201):
{ category object }
```

### Update Category
```
PUT /categories/:id

Body:
{
  "name": "Updated Name",
  "color": "#0000FF"
}

Response (200):
{ category object }
```

### Delete Category
```
DELETE /categories/:id

Response (204): No Content
```

---

## Error Responses

### 400 Bad Request
```json
{
  "error": "Invalid input",
  "details": "Email is required"
}
```

### 401 Unauthorized
```json
{
  "error": "Unauthorized",
  "details": "Invalid token"
}
```

### 403 Forbidden
```json
{
  "error": "Forbidden",
  "details": "You don't have permission"
}
```

### 404 Not Found
```json
{
  "error": "Not found",
  "details": "Resource not found"
}
```

### 500 Internal Server Error
```json
{
  "error": "Internal server error",
  "details": "Something went wrong"
}
```

---

## 📌 Status Codes

| Code | Meaning |
|------|----------|
| 200 | OK |
| 201 | Created |
| 204 | No Content |
| 400 | Bad Request |
| 401 | Unauthorized |
| 403 | Forbidden |
| 404 | Not Found |
| 500 | Internal Server Error |

---

Documentation em desenvolvimento...
