# User Management API Documentation

## Overview

The **User Management API** provides endpoints for:

- User Registration
- User Login
- Get User Details

**Base URL**

```text
https://api.example.com/v1
```

---

## Table of Contents

1. [Login API](#1-login-api)
2. [Register API](#2-register-api)
3. [Get User API](#3-get-user-api)
4. [Common Request Headers](#common-request-headers)
5. [Common Error Responses](#common-error-responses)
6. [API Workflow](#api-workflow)
7. [API Summary](#api-summary)

---

## Common Request Headers

| Header | Required | Description |
|---------|----------|-------------|
| Content-Type | Yes | `application/json` |
| Accept | Yes | `application/json` |
| Authorization | Required for protected APIs | Bearer Token |

---

## 1. Login API

### Endpoint Details

| Property | Value |
|----------|-------|
| Method | POST |
| Endpoint | `/login` |
| Authentication | No |

### Request Headers

| Header | Value |
|--------|-------|
| Content-Type | application/json |
| Accept | application/json |

### Request Body

```json
{
  "email": "john@example.com",
  "password": "Password@123"
}
```

### Request Body Parameters

| Field | Type | Required | Description |
|------|------|----------|-------------|
| email | String | Yes | User email |
| password | String | Yes | User password |

### Sample Success Response

```json
{
  "status": "success",
  "message": "Login successful",
  "token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9",
  "user": {
    "id": 101,
    "name": "John Doe",
    "email": "john@example.com"
  }
}
```

### Error Responses

#### 401 Unauthorized

```json
{
  "status": "error",
  "message": "Invalid email or password"
}
```

#### 400 Bad Request

```json
{
  "status": "error",
  "message": "Email and password are required"
}
```

---

## 2. Register API

### Endpoint Details

| Property | Value |
|----------|-------|
| Method | POST |
| Endpoint | `/register` |
| Authentication | No |

### Request Headers

| Header | Value |
|--------|-------|
| Content-Type | application/json |
| Accept | application/json |

### Request Body

```json
{
  "name": "John Doe",
  "email": "john@example.com",
  "password": "Password@123",
  "phone": "9876543210"
}
```

### Request Body Parameters

| Field | Type | Required | Description |
|------|------|----------|-------------|
| name | String | Yes | Full name |
| email | String | Yes | Email address |
| password | String | Yes | User password |
| phone | String | No | Mobile number |

### Sample Success Response

```json
{
  "status": "success",
  "message": "User registered successfully",
  "userId": 101
}
```

### Error Responses

#### 409 Conflict

```json
{
  "status": "error",
  "message": "Email already registered"
}
```

#### 400 Bad Request

```json
{
  "status": "error",
  "message": "Invalid input data"
}
```

---

## 3. Get User API

### Endpoint Details

| Property | Value |
|----------|-------|
| Method | GET |
| Endpoint | `/users/{id}` |
| Authentication | Yes |

### Request Headers

| Header | Value |
|--------|-------|
| Authorization | Bearer Token |
| Accept | application/json |

### Path Parameter

| Parameter | Type | Description |
|-----------|------|-------------|
| id | Integer | User ID |

### Sample Request

```http
GET /users/101 HTTP/1.1
Authorization: Bearer eyJhbGciOiJIUzI1Ni...
```

### Sample Success Response

```json
{
  "status": "success",
  "data": {
    "id": 101,
    "name": "John Doe",
    "email": "john@example.com",
    "phone": "9876543210"
  }
}
```

### Error Responses

#### 401 Unauthorized

```json
{
  "status": "error",
  "message": "Authentication required"
}
```

#### 404 Not Found

```json
{
  "status": "error",
  "message": "User not found"
}
```

---

## Common Error Responses

| Status Code | Error | Description |
|-------------|-------|-------------|
| 400 | Bad Request | Invalid request |
| 401 | Unauthorized | Authentication failed |
| 403 | Forbidden | Access denied |
| 404 | Not Found | Resource not found |
| 409 | Conflict | Duplicate resource |
| 500 | Internal Server Error | Server error |

---

## API Workflow

- User Registration
  - Fill in registration form.
  - Validate user input.
  - Save user information.
  - Return success response.

- User Login
  - Enter email and password.
  - Validate credentials.
  - Generate JWT token.
  - Return authentication token.

- Get User Details
  - Send Bearer Token.
  - Pass user ID.
  - Verify authentication.
  - Return user information.

---

## API Summary

| API | Method | Endpoint | Authentication |
|-----|--------|----------|----------------|
| Register | POST | `/register` | No |
| Login | POST | `/login` | No |
| Get User | GET | `/users/{id}` | Yes |

---

## Markdown Concepts Used

- Headings (`#`, `##`, `###`)
- Tables
- Nested Lists
- JSON Code Blocks
- HTTP Code Block
- Horizontal Rules (`---`)
- Bold Text
- Inline Code# User Management API Documentation

## Overview

The **User Management API** provides endpoints for:

- User Registration
- User Login
- Get User Details

**Base URL**

```text
https://api.example.com/v1
```

---

## Table of Contents

1. [Login API](#1-login-api)
2. [Register API](#2-register-api)
3. [Get User API](#3-get-user-api)
4. [Common Request Headers](#common-request-headers)
5. [Common Error Responses](#common-error-responses)
6. [API Workflow](#api-workflow)
7. [API Summary](#api-summary)

---

## Common Request Headers

| Header | Required | Description |
|---------|----------|-------------|
| Content-Type | Yes | `application/json` |
| Accept | Yes | `application/json` |
| Authorization | Required for protected APIs | Bearer Token |

---

## 1. Login API

### Endpoint Details

| Property | Value |
|----------|-------|
| Method | POST |
| Endpoint | `/login` |
| Authentication | No |

### Request Headers

| Header | Value |
|--------|-------|
| Content-Type | application/json |
| Accept | application/json |

### Request Body

```json
{
  "email": "john@example.com",
  "password": "Password@123"
}
```

### Request Body Parameters

| Field | Type | Required | Description |
|------|------|----------|-------------|
| email | String | Yes | User email |
| password | String | Yes | User password |

### Sample Success Response

```json
{
  "status": "success",
  "message": "Login successful",
  "token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9",
  "user": {
    "id": 101,
    "name": "John Doe",
    "email": "john@example.com"
  }
}
```

### Error Responses

#### 401 Unauthorized

```json
{
  "status": "error",
  "message": "Invalid email or password"
}
```

#### 400 Bad Request

```json
{
  "status": "error",
  "message": "Email and password are required"
}
```

---

## 2. Register API

### Endpoint Details

| Property | Value |
|----------|-------|
| Method | POST |
| Endpoint | `/register` |
| Authentication | No |

### Request Headers

| Header | Value |
|--------|-------|
| Content-Type | application/json |
| Accept | application/json |

### Request Body

```json
{
  "name": "John Doe",
  "email": "john@example.com",
  "password": "Password@123",
  "phone": "9876543210"
}
```

### Request Body Parameters

| Field | Type | Required | Description |
|------|------|----------|-------------|
| name | String | Yes | Full name |
| email | String | Yes | Email address |
| password | String | Yes | User password |
| phone | String | No | Mobile number |

### Sample Success Response

```json
{
  "status": "success",
  "message": "User registered successfully",
  "userId": 101
}
```

### Error Responses

#### 409 Conflict

```json
{
  "status": "error",
  "message": "Email already registered"
}
```

#### 400 Bad Request

```json
{
  "status": "error",
  "message": "Invalid input data"
}
```

---

## 3. Get User API

### Endpoint Details

| Property | Value |
|----------|-------|
| Method | GET |
| Endpoint | `/users/{id}` |
| Authentication | Yes |

### Request Headers

| Header | Value |
|--------|-------|
| Authorization | Bearer Token |
| Accept | application/json |

### Path Parameter

| Parameter | Type | Description |
|-----------|------|-------------|
| id | Integer | User ID |

### Sample Request

```http
GET /users/101 HTTP/1.1
Authorization: Bearer eyJhbGciOiJIUzI1Ni...
```

### Sample Success Response

```json
{
  "status": "success",
  "data": {
    "id": 101,
    "name": "John Doe",
    "email": "john@example.com",
    "phone": "9876543210"
  }
}
```

### Error Responses

#### 401 Unauthorized

```json
{
  "status": "error",
  "message": "Authentication required"
}
```

#### 404 Not Found

```json
{
  "status": "error",
  "message": "User not found"
}
```

---

## Common Error Responses

| Status Code | Error | Description |
|-------------|-------|-------------|
| 400 | Bad Request | Invalid request |
| 401 | Unauthorized | Authentication failed |
| 403 | Forbidden | Access denied |
| 404 | Not Found | Resource not found |
| 409 | Conflict | Duplicate resource |
| 500 | Internal Server Error | Server error |

---

## API Workflow

- User Registration
  - Fill in registration form.
  - Validate user input.
  - Save user information.
  - Return success response.

- User Login
  - Enter email and password.
  - Validate credentials.
  - Generate JWT token.
  - Return authentication token.

- Get User Details
  - Send Bearer Token.
  - Pass user ID.
  - Verify authentication.
  - Return user information.

---

## API Summary

| API | Method | Endpoint | Authentication |
|-----|--------|----------|----------------|
| Register | POST | `/register` | No |
| Login | POST | `/login` | No |
| Get User | GET | `/users/{id}` | Yes |

---

## Markdown Concepts Used

- Headings (`#`, `##`, `###`)
- Tables
- Nested Lists
- JSON Code Blocks
- HTTP Code Block
- Horizontal Rules (`---`)
- Bold Text
- Inline Code
