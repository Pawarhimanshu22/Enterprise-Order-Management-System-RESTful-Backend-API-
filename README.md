# 🏢 Enterprise Order Management System (EOMS)

A **production-inspired RESTful backend application** built using **Java, Spring Boot, and MySQL** that demonstrates how enterprise systems handle **customers, addresses, products, orders, and order items** with proper data modeling, validation, and API design.

This project focuses on **clean architecture, data safety, and real-world backend practices** rather than just CRUD operations.

---

## 🚀 Key Highlights

* RESTful APIs following HTTP & REST standards
* Enterprise-grade database design (normalized + intentional denormalization)
* Customer-owned **address snapshots** for data safety
* Complete **Order Lifecycle Management**
* Clean separation of layers (Controller, Service, Repository)
* JSON-based request/response handling
* Ready for future enhancements like JWT, microservices, and UI integration

---

## 🧠 Core Design Philosophy

> **Enterprise systems prefer data safety over strict normalization.**

* Addresses are stored as **customer-owned snapshots**, not shared entities
* Prevents accidental updates, cascading deletes, and history corruption
* Ensures **immutability of order data** for auditing and compliance

This approach reflects how **real-world enterprise systems** are designed.

---

## 🏗️ System Architecture

```
Client (Postman / UI)
        ↓
REST Controllers
        ↓
Service Layer (Business Logic)
        ↓
Repository Layer (JPA / Hibernate)
        ↓
MySQL Database
```

---

## 📦 Domain Model

> **Base Package:** `com.himanshu.ecommerce`

### 👤 Customer

* Manages customer identity
* Can have **multiple contact mechanisms (addresses)**

### 📍 Contact Mechanism (Address Snapshot)

* Stores customer-owned address data
* Supports SHIPPING / BILLING / HOME / OFFICE types
* Prevents shared-address side effects

### 📦 Product

* Product catalogue with SKU, price, stock, and status

### 🧾 Order Header

* Represents a customer order
* Tracks order status, payment status, and total amount
* References **shipping & billing address snapshots**

### 📄 Order Item

* Line items within an order
* Tracks quantity, pricing, and item-level status

---

## 🗃️ Database Tables

* `customer`
* `contact_mechanism`
* `product`
* `order_header`
* `order_item`

All tables are designed with:

* Proper primary & foreign keys
* Referential integrity
* Enterprise-friendly naming conventions

---

## 🔗 REST API Endpoints

### 📌 Order APIs

| Method | Endpoint            | Description            |
| ------ | ------------------- | ---------------------- |
| POST   | `/orders`           | Create a new order     |
| GET    | `/orders/{orderId}` | Retrieve order details |
| PUT    | `/orders/{orderId}` | Update order info      |
| DELETE | `/orders/{orderId}` | Delete an order        |

### 📌 Order Item APIs

| Method | Endpoint                           | Description       |
| ------ | ---------------------------------- | ----------------- |
| POST   | `/orders/{orderId}/items`          | Add item to order |
| PUT    | `/orders/{orderId}/items/{itemId}` | Update order item |
| DELETE | `/orders/{orderId}/items/{itemId}` | Remove order item |

---

## 🧪 Sample Scenarios Covered

* Create an order with multiple products
* Retrieve full order details (customer + items)
* Update item quantity
* Add new items to an existing order
* Remove items from an order
* Delete an entire order

All scenarios are tested using **Postman**.

---

## 🛠️ Tech Stack

> **Project Structure:** Standard layered Spring Boot architecture under `com.himanshu.ecommerce`

* **Java**
* **Spring Boot**
* **Spring Data JPA (Hibernate)**
* **MySQL**
* **Postman** (API testing)

---

## 📂 Project Structure

```
src/main/java
 └── com.himanshu.ecommerce
     ├── customer
     ├── contact
     ├── product
     ├── order
     ├── config
     └── exception
```

---

## 🔒 Future Enhancements

* JWT-based Authentication & Authorisation
* Role-based access control (ADMIN / USER)
* Inventory reservation logic
* Microservices decomposition
* Frontend UI integration
* Docker & Cloud deployment

---

## 📸 API Testing

All endpoints are tested using **Postman**.
Screenshots of successful API executions are included as part of the submission.

---

## 🎯 Learning Outcomes

* Real-world database modelling decisions
* RESTful API best practices
* Enterprise-level backend thinking
* Trade-offs between normalisation and data safety

---

## 👨‍💻 Author

**Project Package Name:** `com.himanshu.ecommerce`

**Himanshu Pawar**
Information Technology Engineering
Backend Developer (Java & Spring Boot)

---

⭐ *If you like this project, feel free to star the repository and explore further enhancements!*
