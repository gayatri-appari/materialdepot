# Material Depot — Full-Stack E-commerce Starter

React + Vite frontend, Spring Boot 3 / Java 17 backend, MySQL database.

## Features
- Responsive storefront with search, category filtering and product cards
- Product details, cart saved in localStorage and checkout
- Customer registration/login (passwords BCrypt-hashed)
- Product CRUD endpoints and categories endpoint
- Create/list orders, order items and order status update
- Seed demo categories and products at startup
- Basic admin page for product creation and order status updates
- API documentation via Springdoc Swagger UI

> Security note: this is a local development/demo project. Before public production use, add authenticated/role-protected admin APIs, JWT/session-based authorization, rate limiting, payment-provider verification, image upload storage, audit logging, and deployment secrets management. The demo login endpoint verifies credentials but does not issue an authentication token.

## Requirements
- Java 17+
- Maven 3.9+
- Node.js 20+
- MySQL 8+

## 1. Database
Create the database:
```sql
CREATE DATABASE material_depot CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci;
```
Edit `backend/src/main/resources/application.properties` and set your MySQL username/password.

## 2. Run backend
```bash
cd backend
mvn spring-boot:run
```
Backend: http://localhost:8080  
Swagger UI: http://localhost:8080/swagger-ui.html

## 3. Run frontend (new terminal)
```bash
cd frontend
npm install
npm run dev
```
Frontend: http://localhost:5173

## Demo accounts
Register a customer through the UI. To access the demo admin page, register with email `admin@materialdepot.local`; this is only a demo convenience and is NOT safe for a public deployment. Remove this shortcut and implement real server-side roles before deploying.

## Main API routes
- `GET /api/products`, `GET /api/products/{id}`, `GET /api/products?category=Tiles&search=white`
- `POST /api/products`, `PUT /api/products/{id}`, `DELETE /api/products/{id}`
- `GET /api/categories`
- `POST /api/auth/register`, `POST /api/auth/login`
- `POST /api/orders`, `GET /api/orders`, `GET /api/orders/{id}`, `PATCH /api/orders/{id}/status`

All prices are demo INR values. Product images use remote Unsplash URLs.
