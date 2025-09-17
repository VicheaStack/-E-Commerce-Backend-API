# 🛍️ E-Commerce Backend API

A modern, robust e-commerce backend API built with **Spring Boot 3**, featuring JWT authentication, product management, and comprehensive API documentation. Perfect for showcasing full-stack development skills in your portfolio.

![Java](https://img.shields.io/badge/Java-21-orange)
![Spring Boot](https://img.shields.io/badge/Spring%20Boot-3.3.0-brightgreen)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-15-blue)
![JWT](https://img.shields.io/badge/JWT-Auth-yellow)

## 🚀 Features

- **🔐 Secure JWT Authentication** - Register, login, and role-based access control
- **🛒 Product Management** - Full CRUD operations for products
- **📚 Category System** - Organize products into categories
- **👥 User Management** - User profiles and administration
- **📖 OpenAPI Documentation** - Interactive API docs with Swagger UI
- **🧪 Validation** - Comprehensive input validation
- **🗃️ PostgreSQL Integration** - Robust data persistence
- **🚀 High Performance** - Optimized with MapStruct and Lombok

## 🛠️ Tech Stack

- **Java 21**
- **Spring Boot 3.3.0**
- **Spring Security** with JWT
- **PostgreSQL** Database
- **Spring Data JPA**
- **MapStruct** for efficient object mapping
- **Lombok** for reduced boilerplate code
- **SpringDoc OpenAPI** for API documentation
- **Maven** for dependency management

## 📋 API Endpoints

### Authentication
| Method | Endpoint | Description |
|--------|----------|-------------|
| POST | `/api/auth/register` | Register a new user |
| POST | `/api/auth/login` | Login and receive JWT token |
| GET | `/api/auth/profile` | Get current user profile |

### Products
| Method | Endpoint | Description |
|--------|----------|-------------|
| GET | `/api/products` | Get all products (with pagination) |
| GET | `/api/products/{id}` | Get product by ID |
| POST | `/api/products` | Create new product (Admin only) |
| PUT | `/api/products/{id}` | Update product (Admin only) |
| DELETE | `/api/products/{id}` | Delete product (Admin only) |

### Categories
| Method | Endpoint | Description |
|--------|----------|-------------|
| GET | `/api/categories` | Get all categories |
| POST | `/api/categories` | Create new category (Admin only) |

## 🔧 Installation & Setup

1. **Clone the repository**
   ```bash
   git clone https://github.com/yourusername/ecommerce-backend.git
   cd ecommerce-backend
   ```

2. **Set up PostgreSQL database**
   ```sql
   CREATE DATABASE ecommerce_db;
   CREATE USER ecommerce_user WITH PASSWORD 'your_password';
   GRANT ALL PRIVILEGES ON DATABASE ecommerce_db TO ecommerce_user;
   ```

3. **Configure application properties**
   ```properties
   # src/main/resources/application.properties
   spring.datasource.url=jdbc:postgresql://localhost:5432/ecommerce_db
   spring.datasource.username=ecommerce_user
   spring.datasource.password=your_password
   spring.jpa.hibernate.ddl-auto=update
   
   jwt.secret=your-jwt-secret-key-at-least-256-bits-long
   jwt.expiration=86400000
   ```

4. **Build and run the application**
   ```bash
   mvn clean install
   mvn spring-boot:run
   ```

The API will be available at `http://localhost:8080`

## 📖 API Documentation

Once the application is running, access the interactive API documentation:

- **Swagger UI**: http://localhost:8080/swagger-ui.html
- **OpenAPI JSON**: http://localhost:8080/v3/api-docs

## 🧪 Testing the API

### 1. Register a new user
```bash
curl -X POST "http://localhost:8080/api/auth/register" \
  -H "Content-Type: application/json" \
  -d '{
    "username": "johndoe",
    "email": "john@example.com",
    "password": "password123",
    "firstName": "John",
    "lastName": "Doe"
  }'
```

### 2. Login to get JWT token
```bash
curl -X POST "http://localhost:8080/api/auth/login" \
  -H "Content-Type: application/json" \
  -d '{
    "username": "johndoe",
    "password": "password123"
  }'
```

### 3. Use the token to access protected endpoints
```bash
curl -H "Authorization: Bearer YOUR_JWT_TOKEN" \
  "http://localhost:8080/api/products"
```

## 🗂️ Project Structure

```
src/
├── main/
│   ├── java/com/example/ecommerceapplication/
│   │   ├── config/           # Configuration classes
│   │   ├── controller/       # REST API controllers
│   │   ├── dto/             # Data Transfer Objects
│   │   ├── exception/       # Exception handling
│   │   ├── model/           # Entity classes
│   │   ├── repository/      # Data access layer
│   │   ├── security/        # JWT and Security config
│   │   ├── service/         # Business logic layer
│   │   └── EcommerceApplication.java
│   └── resources/
│       ├── application.properties
│       └── static/
└── test/                    # Test classes
```

## 🐳 Docker Deployment

The application can be easily containerized with Docker:

1. **Build the Docker image**
   ```bash
   docker build -t ecommerce-backend .
   ```

2. **Run the container**
   ```bash
   docker run -p 8080:8080 \
     -e SPRING_DATASOURCE_URL=jdbc:postgresql://host.docker.internal:5432/ecommerce_db \
     -e SPRING_DATASOURCE_USERNAME=ecommerce_user \
     -e SPRING_DATASOURCE_PASSWORD=your_password \
     ecommerce-backend
   ```

## 🌟 Portfolio Highlights

- **Modern Java Development**: Demonstrates proficiency with Java 21 and latest Spring Boot features
- **REST API Design**: Clean, well-structured RESTful endpoints following best practices
- **Security Implementation**: JWT authentication with Spring Security
- **Database Management**: PostgreSQL integration with Spring Data JPA
- **Code Quality**: Utilizes Lombok and MapStruct for clean, efficient code
- **API Documentation**: Comprehensive OpenAPI/Swagger documentation
- **Testing**: Includes unit and integration tests

## 📝 License

This project is open source and available under the [MIT License](LICENSE).

## 🤝 Contributing

Contributions, issues, and feature requests are welcome! Feel free to check [issues page](https://github.com/yourusername/ecommerce-backend/issues).

## 📧 Contact

Your Name - [your.email@example.com](mailto:your.email@example.com)

Project Link: [https://github.com/yourusername/ecommerce-backend](https://github.com/yourusername/ecommerce-backend)

---

⭐️ Feel free to star this repository if you found it helpful for your portfolio!
