# API Documentation

Welcome to the API documentation for **Bazaar**! This API provides a comprehensive suite of endpoints for managing products, categories, orders, users, and AI-assisted recommendations. This README will guide you through the key features and usage of the API.

## Table of Contents

* Overview
* Getting Started
* Authentication
* Products
* Categories
* Orders
* Users
* AI Recommendations
* Error Handling
* API Endpoints
* Swagger Documentation

## Overview

The Bazaar API enables you to perform CRUD operations on products, categories, orders, and users, as well as manage AI-driven recommendations. It is designed to be efficient, scalable, and user-friendly.

## Getting Started

To get started with the API, follow these steps:

### Clone the Repository:

```bash
git clone <git@github.com:yourusername/bazaar.git>
```

### Navigate to the Project Directory:

```bash
cd bazaar
```

### Install Dependencies:

Ensure you have Go installed, then run:

```bash
go mod tidy
```

### Start the Server:

```bash
go run main.go
```

### Access the API:

The API will be running at `http://localhost:9090/api/v1`.

## Authentication

The API uses token-based authentication for secure access. You need to register and log in to obtain a token.

* **Register:** `POST /api/v1/auth/register`
* **Login:** `POST /api/v1/auth/login`
* **Refresh Token:** `POST /api/v1/auth/refresh`

Include the token in the Authorization header for authenticated requests:

```
Authorization: Bearer <your-token>
```

## Products

Manage products with the following endpoints:

* **Add Product:** `POST /api/v1/products/add`
* **Edit Product:** `POST /api/v1/products/edit`
* **Delete Product:** `DELETE /api/v1/products/delete/:id`
* **Get Product:** `GET /api/v1/products/get/:id`
* **List Products:** `POST /api/v1/products/getall`
* **Search Products:** `POST /api/v1/products/search`

### Caching

Product data is cached using Redis for improved performance. When a product is created, edited, or deleted, the corresponding cache entries are invalidated.

## Categories

Manage categories with the following endpoints:

* **Add Category:** `POST /api/v1/categories/add`
* **Edit Category:** `POST /api/v1/categories/edit`
* **Delete Category:** `DELETE /api/v1/categories/delete/:id`
* **Get Category:** `GET /api/v1/categories/get/:id`
* **List Categories:** `POST /api/v1/categories/getall`

## Orders

Manage orders with the following endpoints:

* **Add Order:** `POST /api/v1/orders/add`
* **Edit Order:** `POST /api/v1/orders/edit`
* **Delete Order:** `DELETE /api/v1/orders/delete/:id`
* **Get Order:** `GET /api/v1/orders/get/:id`
* **List Orders:** `POST /api/v1/orders/getall`

## Users

Manage users with the following endpoints:

* **Add User:** `POST /api/v1/users/add`
* **Edit User:** `POST /api/v1/users/edit`
* **Delete User:** `DELETE /api/v1/users/delete/:id`
* **Get User:** `GET /api/v1/users/get/:id`
* **List Users:** `POST /api/v1/users/getall`

## AI Recommendations

Leverage AI to provide personalized product recommendations:

* **Get Recommendations:** `GET /api/v1/recommendations/:userId`
* **Update Preferences:** `POST /api/v1/recommendations/preferences`

## Error Handling

The API returns standard HTTP status codes for errors:

* `400 Bad Request` – Invalid request data.
* `404 Not Found` – Resource not found.
* `500 Internal Server Error` – Server error.

Error responses include a message with details about the error.

## API Endpoints

For detailed information about each endpoint, including request parameters and response formats, refer to the Swagger documentation.

## Swagger Documentation

Explore and interact with the API using Swagger UI:

* **Swagger Documentation:** `http://localhost:9090/swagger/index.html`

### Environment Variables

```
AUTH_HOST=:2222
PRODUCT_HOST=:4444
ORDER_HOST=:5555
USER_HOST=:6666
GATEWAY_HOST=:8080
SERVER_ADDRESS=:9090
```
