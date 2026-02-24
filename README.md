# 🧩 E-Commerce Microservices System

A scalable microservices-based backend for an e-commerce platform built using Spring Boot, Spring Cloud, Kafka, and MongoDB.  
The system consists of independent services for Product, Order, and Payment, coordinated via API Gateway and Service Discovery.

---

## 🚀 Architecture Overview

Client → API Gateway → Microservices  
├── Product Service  
├── Order Service  
└── Payment Service

Service Discovery handled by Eureka Server  
Asynchronous communication via Apache Kafka

---

## 🏗️ Microservices

### 📦 Product Service
Manages product catalog.

**Features**
- Add new products
- Update product details
- Delete products
- Fetch product list
- MongoDB persistence

---

### 🧾 Order Service
Handles order creation and processing.

**Features**
- Create orders
- Validate product availability
- Publish order events to Kafka
- Track order status

---

### 💳 Payment Service
Processes payments for orders.

**Features**
- Receive order events from Kafka
- Process payments
- Update payment status
- Publish payment confirmation

---

## 🌐 API Gateway

Single entry point for all client requests.

**Responsibilities**
- Request routing to services
- Load balancing
- Security (if configured)
- Hides internal service structure

---

## 🧭 Eureka Service Discovery

Registers all microservices dynamically.

**Benefits**
- No hardcoded service URLs
- Automatic service discovery
- Load balancing support

---

## 🔁 Kafka Messaging

Used for asynchronous communication between Order and Payment services.

### Flow:

1. Order Service publishes **OrderCreatedEvent**
2. Kafka topic receives event
3. Payment Service consumes event
4. Payment processed
5. Payment confirmation event published

---

## 🛠️ Tech Stack

### Backend
- Java 17
- Spring Boot
- Spring Cloud
- Spring Data MongoDB
- Spring WebFlux / MVC

### Cloud Components
- Eureka Server
- Spring Cloud Gateway

### Messaging
- Apache Kafka

### Database
- MongoDB

### Build Tool
- Maven

---

## 📂 Project Structure
