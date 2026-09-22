# Employee Management System

A simple full-stack Employee Management System built using **React**, **Spring Boot REST API**, and **MySQL**.

## Technologies Used

- React + Vite
- Java
- Spring Boot
- Spring Web
- Spring Data JPA / Hibernate
- MySQL
- Postman
- XAMPP

## Features

- Add Employee
- Display All Employees
- Update Employee
- Delete Employee
- React frontend connected to Spring Boot REST APIs
- MySQL database integration

## Architecture

```text
React Web Application
        |
        | REST API
        v
Spring Boot REST API
        |
        | Spring Data JPA
        v
MySQL Database
```

## REST API Endpoints

| Operation | Method | Endpoint |
|---|---|---|
| Display All Employees | GET | `http://localhost:8081/employees` |
| Add Employee | POST | `http://localhost:8081/employees` |
| Update Employee | PUT | `http://localhost:8081/employees/{id}` |
| Delete Employee | DELETE | `http://localhost:8081/employees/{id}` |

### Add Employee

```http
POST http://localhost:8081/employees
```

```json
{
  "name": "Ravi",
  "department": "IT",
  "salary": 45000
}
```

### Update Employee

```http
PUT http://localhost:8081/employees/2
```

```json
{
  "name": "Kiran Kumar",
  "department": "HR",
  "salary": 45000
}
```

### Delete Employee

```http
DELETE http://localhost:8081/employees/2
```

## Backend Structure

```text
employee/
├── src/main/java/com/vcube/employee/
│   ├── EmployeeApplication.java
│   ├── controller/
│   │   └── EmployeeController.java
│   ├── model/
│   │   └── Employee.java
│   └── repository/
│       └── EmployeeRepository.java
├── src/main/resources/
│   └── application.properties
└── pom.xml
```

## React Structure

```text
employee-react/
├── src/
│   ├── App.jsx
│   ├── index.css
│   └── main.jsx
├── public/
├── index.html
├── package.json
└── vite.config.js
```

## MySQL Setup

Create the database:

```sql
CREATE DATABASE employee_db;
```

Example `application.properties`:

```properties
spring.datasource.url=jdbc:mysql://localhost:3306/employee_db
spring.datasource.username=root
spring.datasource.password=YOUR_PASSWORD

spring.jpa.hibernate.ddl-auto=update
server.port=8081
```

**Do not upload your real MySQL password to GitHub.**

## Run Backend

1. Start MySQL from XAMPP.
2. Create the `employee_db` database.
3. Configure `application.properties`.
4. Run `EmployeeApplication.java`.
5. Backend runs at:

```text
http://localhost:8081
```

## Run Frontend

Open a terminal inside `employee-react`:

```bash
npm install
npm run dev
```

Open:

```text
http://localhost:5173
```

## CORS

The Spring Boot controller allows the React frontend:

```java
@CrossOrigin(origins = "http://localhost:5173")
```

So:

```text
React       -> localhost:5173
Spring Boot -> localhost:8081
```

can communicate.

## CRUD Flow

```text
                 Employee Management System
                           |
          +----------------+----------------+
          |                |                |
          v                v                v
        CREATE            READ            UPDATE
        POST              GET              PUT
          |                |                |
          +----------------+----------------+
                           |
                           v
                         DELETE
                           |
                           v
                    MySQL Database
```

## Learning Outcomes

This project demonstrates:

- React components
- `useState`
- `useEffect`
- JavaScript `fetch()`
- REST APIs
- HTTP methods
- Spring Boot REST controllers
- `@GetMapping`
- `@PostMapping`
- `@PutMapping`
- `@DeleteMapping`
- Spring Data JPA
- MySQL
- CRUD operations
- CORS

## Author

Employee Management System — learning project using React, Spring Boot REST API, and MySQL.
