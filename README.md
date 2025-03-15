# Nimap_Infotech_Machine_Test

## 📌 Project Overview
This project implements a **Spring Boot CRUD application** with **pagination and relational mapping** between `Category` and `Product` entities. The application follows RESTful API principles and uses **Spring Data JPA** with **MySQL** as the database.

## 🛠️ Tech Stack
- **Spring Boot** (REST API)
- **Spring Data JPA** (ORM)
- **Hibernate** (JPA implementation)
- **MySQL** (Relational Database)
- **Spring Boot Pagination**
- **Spring Boot DevTools** (for hot reloading)
- **Postman** (for API testing)

## 🎯 Features
✅ **Category CRUD operations**
✅ **Product CRUD operations**
✅ **Pagination for fetching categories and products**
✅ **One-to-Many relationship (Category → Products)**
✅ **Server-side validation using Hibernate annotations**

---

## ⚙️ Database Configuration (`application.properties`)
```properties
spring.application.name=NimapMachineTest
spring.datasource.url=jdbc:mysql://localhost:3306/nimap2?useSSL=false&allowPublicKeyRetrieval=true&serverTimezone=UTC
spring.datasource.username=root
spring.datasource.password=password
spring.datasource.driver-class-name=com.mysql.cj.jdbc.Driver

spring.jpa.hibernate.ddl-auto=update
spring.jpa.show-sql=true
```
> **Note:** Ensure MySQL is running and the database `nimap2` is created before starting the application.

---

## 📂 Project Structure
```
NimapMachineTest
├── src
│   ├── main
│   │   ├── java
│   │   │   ├── com.nimap
│   │   │   │   ├── controller
│   │   │   │   │   ├── CategoryController.java
│   │   │   │   │   ├── ProductController.java
│   │   │   │   ├── entity
│   │   │   │   │   ├── Category.java
│   │   │   │   │   ├── Product.java
│   │   │   │   ├── repository
│   │   │   │   │   ├── CategoryRepository.java
│   │   │   │   │   ├── ProductRepository.java
│   │   │   │   ├── service
│   │   │   │   │   ├── CategoryService.java
│   │   │   │   │   ├── ProductService.java
│   │   │   │   ├── NimapApplication.java
├── pom.xml
└── README.md
```

---

## 📌 API Endpoints

### **Category APIs** (`/api/categories`)
| Method | Endpoint | Description |
|--------|----------|-------------|
| `GET` | `/api/categories?page=1` | Fetch paginated categories |
| `POST` | `/api/categories` | Create a new category |
| `GET` | `/api/categories/{id}` | Fetch category by ID |
| `PUT` | `/api/categories/{id}` | Update category by ID |
| `DELETE` | `/api/categories/{id}` | Delete category by ID |

### **Product APIs** (`/api/products`)
| Method | Endpoint | Description |
|--------|----------|-------------|
| `GET` | `/api/products?page=2` | Fetch paginated products |
| `POST` | `/api/products` | Create a new product |
| `GET` | `/api/products/{id}` | Fetch product by ID (with category details) |
| `PUT` | `/api/products/{id}` | Update product by ID |
| `DELETE` | `/api/products/{id}` | Delete product by ID |

---

## 🔄 Running the Application
1. **Clone the repository**
   ```sh
   git clone https://github.com/your-repo.git
   cd NimapMachineTest
   ```
2. **Update MySQL credentials** in `application.properties`.
3. **Build and run the application**
   ```sh
   mvn clean spring-boot:run
   ```
4. **Test the APIs** using **Postman**

---

## 📝 Notes
- The application uses **Spring Data JPA pagination** (`Pageable`) to fetch paginated results.
- **One-to-Many Mapping:** Each `Category` can have multiple `Products`.
