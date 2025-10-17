# Spring Boot REST API

A simple RESTful API built with Spring Boot 3.5.6 and H2 database for managing user data.

## Features

- RESTful API endpoints for user management
- H2 in-memory database with file persistence
- JPA/Hibernate for data persistence
- Lombok for reducing boilerplate code
- H2 Console for database management

## Technologies Used

- **Java 21**
- **Spring Boot 3.5.6**
- **Spring Data JPA**
- **H2 Database**
- **Lombok**
- **Maven**

## Prerequisites

- Java 21 or higher
- Maven 3.6+

## Getting Started

### 1. Clone the repository

```bash
git clone https://github.com/Safkatul-Islam/Simple-Rest-Api.git
cd Simple-Rest-Api
```

### 2. Configure the application

Copy the example configuration file:

```bash
cp src/main/resources/application.properties.example src/main/resources/application.properties
```

Update the database configuration in `application.properties` if needed.

### 3. Run the application

```bash
mvnw spring-boot:run
```

Or on Windows:

```bash
mvnw.cmd spring-boot:run
```

The application will start on `http://localhost:8080`

## API Endpoints

### User Management

| Method | Endpoint           | Description          |
|--------|--------------------|----------------------|
| POST   | `/api/v1/users`    | Create a new user    |
| GET    | `/api/v1/users`    | Get all users        |

### Request/Response Examples

**Create User (POST /api/v1/users)**

Request Body:
```json
{
  "name": "John Doe",
  "email": "john.doe@example.com"
}
```

Response:
```json
{
  "id": 1,
  "name": "John Doe",
  "email": "john.doe@example.com"
}
```

**Get All Users (GET /api/v1/users)**

Response:
```json
[
  {
    "id": 1,
    "name": "John Doe",
    "email": "john.doe@example.com"
  },
  {
    "id": 2,
    "name": "Jane Smith",
    "email": "jane.smith@example.com"
  }
]
```

## H2 Database Console

Access the H2 console at: `http://localhost:8080/h2-console`

**Default credentials:**
- JDBC URL: `jdbc:h2:file:./data/testdb`
- Username: `your_username`
- Password: `your_password`

## Project Structure

```
src/
├── main/
│   ├── java/
│   │   └── com/api/production/api/
│   │       ├── ApiForCrApplication.java      # Main application class
│   │       ├── controller/
│   │       │   └── UserController.java       # REST endpoints
│   │       ├── entity/
│   │       │   └── User.java                 # User entity
│   │       ├── repository/
│   │       │   └── UserRepository.java       # Data access layer
│   │       └── service/
│   │           └── UserService.java          # Business logic
│   └── resources/
│       └── application.properties            # Configuration
└── test/
    └── java/                                 # Test classes
```

## Building for Production

Create a JAR file:

```bash
mvnw clean package
```

Run the JAR:

```bash
java -jar target/api-0.0.1-SNAPSHOT.jar
```

## License

This project is open source and available under the [MIT License](LICENSE).

---

⭐ If you find this project helpful, please give it a star!

