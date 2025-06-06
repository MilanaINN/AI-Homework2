# JSONPlaceholder API Clone

This is a Spring Boot implementation of the JSONPlaceholder API with added JWT authentication and PostgreSQL database support.

## Features

- Full REST API implementation matching JSONPlaceholder endpoints
- JWT-based authentication
- PostgreSQL database with proper schema
- Docker and Docker Compose support
- Secure password hashing
- Input validation
- Proper error handling

## Prerequisites

- Java 17 or higher
- Gradle 8.5 or higher
- Docker and Docker Compose
- PostgreSQL (if running without Docker)

## Getting Started

### Running with Docker

1. Clone the repository
2. Build and start the containers:
   ```bash
   docker-compose up --build
   ```

The application will be available at `http://localhost:8080`

### Running Locally

1. Clone the repository
2. Update `application.properties` with your database credentials
3. Build the project:
   ```bash
   ./gradlew build
   ```
4. Run the application:
   ```bash
   ./gradlew bootRun
   ```

## API Endpoints

### Authentication

- `POST /api/auth/register` - Register a new user
- `POST /api/auth/login` - Login and get JWT token

### Users

- `GET /api/users` - Get all users
- `GET /api/users/{id}` - Get user by ID
- `POST /api/users` - Create a new user
- `PUT /api/users/{id}` - Update a user
- `DELETE /api/users/{id}` - Delete a user

## Security

- All endpoints except `/api/auth/**` require JWT authentication
- Include the JWT token in the Authorization header:
  ```
  Authorization: Bearer <your_token>
  ```

## Development

### Project Structure

```
src/main/java/com/jsonplaceholder/api/
├── controller/     # REST controllers
├── model/         # Entity classes
├── repository/    # Data access layer
├── security/      # Security configuration
└── service/       # Business logic
```

### Testing

Run the tests with:
```bash
./gradlew test
```

## License

This project is licensed under the MIT License. 