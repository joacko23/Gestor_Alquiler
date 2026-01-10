<!-- README – Gestor_Alquiler Backend (Spring Boot) -->

<p align="center">
  <img src="https://capsule-render.vercel.app/api?type=waving&color=0:004e92,100:000428&height=150&section=header&text=Gestor%20Alquiler%20–%20Backend&fontSize=40&fontColor=ffffff" />
</p>

<p align="center">
  <b>Backend REST API · Java · Spring Boot</b><br>
  <i>Rental management system focused on clean architecture and backend design patterns</i>
</p>

---

## 🧠 Overview

**Gestor_Alquiler_Backend** is a **backend-first REST API** developed with **Spring Boot**, designed to manage the rental of different types of assets through a flexible and extensible domain model.

The system supports:

- 🚗 **Vehicles** (cars, motorcycles, trucks — rented per hour)
- 📦 **Appliances** (electrodomésticos — rented per day)

The project focuses on **backend architecture**, applying **SOLID principles**, **object-oriented design**, and well-known **design patterns** such as **Factory Method** and **Strategy**.

Authentication and authorization are handled using **JWT**, ensuring a stateless and secure API.

---

## ✅ Features

### 🔐 Authentication & Security
- Login with email and password
- JWT-based authentication
- Stateless security configuration
- CORS configured for frontend consumption

### 🚗 Rental Management
- Create, update and delete rentals
- Hour-based pricing for vehicles
- Day-based pricing for appliances
- Automatic rental cost calculation
- Availability validation to prevent double booking

### 📦 Inventory (Alquilables)
- Separate domain models for vehicles and appliances
- Availability tracking
- Full CRUD operations
- DTO-based API communication
- Factory pattern for asset creation
- Strategy pattern for pricing calculation

### 👤 User Management
- User authentication
- Role-based access
- Rentals associated with authenticated users

---

## 🧱 Architecture & Design

### 🧩 Layered Backend Architecture
- `controllers` — REST API endpoints
- `services` — business logic
- `repositories` — data persistence (JPA)
- `entities` — domain models
- `dtos` — API contracts
- `strategies` — pricing algorithms
- `factory` — alquilable instantiation

### 🧠 Design Patterns Applied
- **Factory Method** → creation of different rentable asset types
- **Strategy** → interchangeable pricing algorithms
- **DTO + Mapper** → separation between API and domain
- **Singleton** → applied in DAO layer (legacy version)

### 🔧 Spring Ecosystem
- Spring Web
- Spring Data JPA
- Hibernate
- Spring Security
- ModelMapper

---

## 🗄️ Database Model (Simplified)

**Users**
- id
- email
- password
- role

**Alquilables**
- id
- type (vehicle / appliance)
- brand
- available
- subtype-specific fields

**Rentals**
- id
- user_id (FK)
- alquilable_id (FK)
- start_date
- end_date
- total_cost

---

## 📡 API Endpoints (Summary)

### 🔐 Authentication
| Method | Endpoint      | Description        |
|------|---------------|--------------------|
| POST | `/auth/login` | Returns JWT token  |

### 🚗 Alquilables
| Method | Endpoint             | Description        |
|------|----------------------|--------------------|
| GET  | `/alquilables`       | List all assets    |
| POST | `/alquilables`       | Create asset       |
| PUT  | `/alquilables/{id}`  | Update asset       |
| DELETE | `/alquilables/{id}` | Delete asset       |

### 📄 Rentals
| Method | Endpoint         | Description                     |
|------|------------------|---------------------------------|
| POST | `/rentals`       | Create rental if available      |
| GET  | `/rentals/user`  | Rentals by authenticated user  |
| DELETE | `/rentals/{id}` | Cancel rental                   |

---

## ▶️ How to Run

### ✅ 1. Clone the repository
```bash
git clone https://github.com/joacko23/Gestor_Alquiler_Backend.git
cd Gestor_Alquiler_Backend

```

### ✅ 2. Configure database (MySQL)
Create database:
```bash
CREATE DATABASE gestor_alquiler;
```
Configure credentials in application.properties:
```bash
spring.datasource.url=jdbc:mysql://localhost:3306/gestor_alquiler
spring.datasource.username=root
spring.datasource.password=tu_password
spring.jpa.hibernate.ddl-auto=update
```
### ✅ 3. Run the app
```bash
mvn spring-boot:run
```
Backend available at:
➡️ http://localhost:8080

## 🛠️ Technologies

Java 17+

Spring Boot

Spring Security + JWT

JPA / Hibernate

MySQL

ModelMapper

## 👨‍💻 Author

**Joaquín Domenech**  
Backend Developer — Java & Spring Boot  
📧 joackodomenech@gmail.com  

<p align="center"> <img src="https://capsule-render.vercel.app/api?type=waving&color=0:000428,100:004e92&height=150&section=footer" /> </p> 


