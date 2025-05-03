# Fiber-Basic
This is a simple RESTful API built with [Fiber](https://github.com/gofiber/fiber), a fast web framework for Go. It supports CRUD operations for managing books, authentication using JWT, Swagger documentation, file uploads, and environment configuration access.

## 🚀 Features

- CRUD for books (`GET`, `POST`, `PUT`, `DELETE`)
- JWT Authentication with role-based access
- Swagger API Documentation (`/swagger/index.html`)
- HTML rendering using templates
- File upload support
- Load environment variables with `.env`

## 📦 Tech Stack

- Go
- Fiber Framework
- JWT (via `github.com/golang-jwt/jwt/v4`)
- Swagger (via `github.com/gofiber/swagger`)
- HTML Template Engine
- dotenv (`github.com/joho/godotenv`)

## 🧪 Endpoints

| Method | Endpoint         | Description             | Auth Required |
|--------|------------------|-------------------------|---------------|
| POST   | `/login`         | Login and get JWT token | ❌            |
| GET    | `/books`         | Get all books           | ✅            |
| GET    | `/books/:id`     | Get book by ID          | ✅            |
| POST   | `/books`         | Create a new book       | ✅            |
| PUT    | `/books/:id`     | Update a book           | ✅            |
| DELETE | `/books/:id`     | Delete a book           | ✅            |
| POST   | `/upload`        | Upload a file           | ✅            |
| GET    | `/config`        | Get env secret value    | ✅            |
| GET    | `/swagger/*`     | Swagger docs            | ❌            |
| GET    | `/test-html`     | Render a sample HTML    | ✅            |

> ⚠️ All authenticated routes require `Authorization: Bearer <token>` header.

## 🔐 Login Details (Demo)

Use the following credentials to test authentication:

```json
{
  "email": "test@test.com",
  "passoword": "password123"
}
```
## ⚙️ Installation & Run
### 1. Clone the repo
git clone [https://github.com/YOUR_USERNAME/fiber-basic.git](https://github.com/chavitdew/Fiber-Basic.git)<br>
cd fiber-basic
### 2. Create .env file
JWT_SECRET=your_jwt_secret<br>
SECRET=some_secret_value
### 3. Install dependencies
go mod tidy
### 4.Generate Swagger Docs
go install github.com/swaggo/swag/cmd/swag@latest<br>
swag init
### 5. Run
go run main.go
