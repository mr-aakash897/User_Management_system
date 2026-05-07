# 🧑‍💼User Management System

A professional, full-stack User Management System built with **Java 17**, **Spring Boot 3**, **MongoDB Atlas**, and a modern **SaaS-style Vanilla Frontend**.<br> This project demonstrates clean layered architecture, secure authentication, and RESTful API best practices.

---

## 🚀 Project Overview
This system provides a secure portal for user onboarding and administrative governance. It implements Role-Based Access Control (RBAC), ensuring that sensitive operations (like viewing the user list or deleting accounts) are restricted to authorized administrators.

### Key Features
- **Secure Registration:** Publicly accessible endpoint for new users.
- **RBAC Security:** Powered by Spring Security with HTTP Basic Authentication.
- **Password Safety:** Industry-standard **BCrypt** hashing for all stored passwords.
- **Modern UI:** Responsive, SaaS-inspired frontend with Glassmorphism and Mesh Gradients.
- **Dynamic Feedback:** Real-time Toast notifications and password visibility toggles.
- **Data Persistence:** Integrated with MongoDB Atlas for cloud-based storage.

---

## 🛠 Tech Stack

### Backend
- **Java 17** & **Spring Boot 3.2+**
- **Spring Security:** HTTP Basic Auth & Method-level Security.
- **Spring Data MongoDB:** For NoSQL database interaction.
- **Lombok:** To reduce boilerplate code.
- **Jakarta Validation:** For API payload verification.

### Frontend
- **HTML5 & CSS3:** Custom Mesh Gradients & SaaS layout (No Frameworks).
- **Vanilla JavaScript:** Fetch API for asynchronous backend communication.

### Database & Tools
- **MongoDB Atlas:** Cloud Database.
- **Postman:** For API testing and documentation.
- **Maven:** Dependency management.

---

## 📂 Project Structure
```text
src/main/java/com/syntecxhub/userManagement
 ├── controller/    # REST API Endpoints
 ├── service/       # Business logic (Interfaces & Impl)
 ├── repository/    # MongoDB Data Access
 ├── model/         # User Entity (@Document)
 ├── dto/           # Data Transfer Objects (Request/Response)
 ├── security/      # Custom UserDetailsService logic
 └── config/        # Security & Password Encoder configurations

src/main/resources
 ├── static/        # Frontend (index.html, css/, js/)
 └── application.properties # Database & Port config

```
---

## 📌 API Documentation
### 1. User Registration (Public)
```POST /api/users/register ```
#### Request Body:
```
JSON
{
  "username": "johndoe",
  "password": "password123",
  "email": "john@example.com",
  "fullName": "John Doe",
  "roles": ["ROLE_USER"]
}
```
### 2. Get All Users (Admin Only)
```GET /api/users```
* Requires: Basic Auth (Admin credentials).

### 3. Get User By ID
```GET /api/users/{id}```
* Requires: Authenticated Session.

### 4. Delete User (Admin Only)
```DELETE /api/users/{id}```
* Requires: Basic Auth (Admin credentials).

---

## 🧪 Postman Testing Guide
### 1. Register a User:
* Send a ```POST``` to ```/api/users/register``` with the JSON body above.
### 2. Setup Authentication:
* In Postman, go to the Authorization tab.
* Select Type: Basic Auth.
* Enter the ```username``` and ```password``` of a user registered with ```ROLE_ADMIN```.
### 3. Access Protected Data:
* Send a ```GET``` to ```/api/users```. If your credentials are correct and you have the Admin role, you will receive the user list.

---

## 🌐 Frontend Usage
The frontend is served directly by the Spring Boot server.
* URL: http://localhost:8080/
* Home: Hero landing with navigation.
* Register: Interactive form with "Show/Hide" password toggle.
* Admin Panel: Secure dashboard requiring Admin credentials to "Sync" and display user cards.

---

## 🗄 Database Configuration
Update ```src/main/resources/application.properties``` with your MongoDB Atlas string:
```
<> Properties
spring.data.mongodb.uri=mongodb+srv://<username>:<password>@cluster.mongodb.net/usermanagement
spring.data.mongodb.database=usermanagement
```

---

## ▶ How to Run

### 1. Clone: ```git clone https://github.com/mr-aakash897/Syntecxhub_User_Management_system.git```
### 2. Build: ```mvn clean install```
### 3. Run: ```mvn spring-boot:run```
### 4. Access: Open ```http://localhost:8080``` in your browser.

---

## ✅ Internship Requirements Checklist

* Spring Boot Layered Architecture
* MongoDB Atlas Integration
* BCrypt Password Encoding
* CRUD Operations
* DTO Pattern Implementation
* Global Error Handling
* Responsive Frontend with API Integration

---

## 📈 Future Enhancements

* JWT Authentication
* Swagger API Documentation
* User Login Page
* Pagination & Search
* Deployment (Render / Railway / AWS)

---

## 👨‍💻 Author
Aakash Chouhan
* GitHub: mr-aakash897
* LinkedIn: [linkedin.com/in/aakash-chouhan-a69a64286](https://www.linkedin.com/in/aakash-chouhan-a69a64286/)

---

### ⭐ Acknowledgements

This project was built as part of an internship task to demonstrate backend development, security, and full-stack fundamentals using Spring Boot.
