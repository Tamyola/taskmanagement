# Task Management API

## Overview

This is a Task Management API built using NestJS. It provides features for managing tasks, user authentication, and role-based access control (using JWT). Admins can manage users and view all tasks, while users can create, read, update, and delete their own tasks.

## Features:
User Management: Registration, login, JWT-based authentication.
Roles: Two roles are supported: USER and ADMIN. Admins can manage users and view all tasks.
Task Management: Users can create, read, update, and delete tasks.
Task Filtering: Users can filter tasks by status, sort by priority or due date, and paginate results.
Authorization: Users can only manage their own tasks. Admins can view all tasks.
Database: PostgreSQL for managing users and tasks with relationships between them.
Error Handling: Validation for inputs and error responses.

Technologies Used
Node.js & NestJS - Framework for building the API.
PostgreSQL - Database for storing users and tasks.
TypeORM - ORM for database interaction.
JWT - JSON Web Token for authentication.
BcryptJS - Password hashing and validation.
Passport-JWT - Authentication middleware.
Class Validator - Data validation.

## Getting Started

### Prerequisites

Before you begin, ensure you have the following installed:

- [Node.js](https://nodejs.org/en/) (LTS version recommended)
- [npm](https://www.npmjs.com/) (comes with Node.js)
- [PostgreSQL](https://www.postgresql.org/download/) (or any preferred SQL database)

Installation:
Clone the repository:

bash
Copy code
git clone https://github.com/Tamyola/taskmanagement.git
cd tmanage-main
Install the dependencies:

bash
Copy code
npm install
Set up the PostgreSQL database:

Make sure PostgreSQL is running on your system.
Create a new database named "task_management"

Create a .env file in the project root and provide the following environment variables:

DATABASE_HOST=localhost
DATABASE_PORT=5432
DATABASE_USER=postgres
DATABASE_PASSWORD=Tamilore1999
DATABASE_NAME=tmanage-main
JWT_SECRET=90dcf7f87881a3b5bb39fc57c598b8696446470db2191a965527f02579c81f7ff3a7317324c1bbbaa38c334a5ff2bd8a0bc5c098da899616863cc44c6f144557

Run the application:
npm run start:dev
The API will be available at http://localhost:3000.

API Endpoints
User Management
GET /user/paginate - Retrieves a paginated list of users.
POST /user/create - Register a new user.
DELETE /user/delete/:id - Deletes a user by their ID

Task Management
GET /task/:paginate - Retrieve all tasks (requires JWT token).
POST /task/:create- Create a new task (requires JWT token).
PATCH /task/update/:taskId - Update an existing task (requires JWT token).
DELETE /task/delete/:taskId - Delete a task by ID (requires JWT token).

Example Requests
Register User

POST /user/create
Content-Type: application/json

{
  "username": "exampleUser",
  "password": "examplePassword"
}

Login User
text
POST /user/paginate 
Content-Type: application/json

{
  "username": "exampleUser",
  "password": "examplePassword"
}

Create Task

POST /task
Authorization: Bearer <your_jwt_token>
Content-Type: application/json

{
  "title": "New Task",
  "description": "Task description",
  "status": "pending",
  "priority": "medium",
  "dueDate": "2024-09-30"
}

Error Handling
The API includes error handling for various scenarios such as:
Invalid input data.
Unauthorized access attempts.
Resource not found errors.

License
This project is licensed under the MIT License - see the LICENSE file for details.


Contributions are welcome! Please feel free to submit a pull request or open an issue.

