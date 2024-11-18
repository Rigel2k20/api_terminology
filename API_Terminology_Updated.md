# API Terminology and Concepts

## What is an API?
**API** stands for **Application Programming Interface**, an interface that allows two applications to communicate with each other.

### Core Concepts
- **Request-Response Cycle**
- **Authentication**
- **Rate Limiting**
  - **Example:**
    ```http
    Rate limit: 100 requests per 15 minutes
    # Rate Limit Response:
    HTTP/1.1 429 Too Many Requests
    {
        "error": "Rate limit exceeded",
        "retry_after": 900
    }
    ```

### Real-World Applications
- **Hotel Booking Apps:**
  - **Example:**
    ```http
    GET /api/hotels/availability
    # Success Response:
    HTTP/1.1 200 OK
    {
        "available_rooms": [
            {"type": "suite", "price": 200},
            {"type": "double", "price": 150}
        ]
    }
    ```

- **Social Login:**
  - **Example:**
    ```http
    POST /api/auth/google
    # Success Response:
    HTTP/1.1 200 OK
    {
        "user_id": "123",
        "token": "abc123xyz"
    }
    ```
  - **Error Response:**
    ```http
    HTTP/1.1 401 Unauthorized
    {
        "error": "Authentication failed"
    }
    ```

---

## Basic Concepts of APIs
### Request Components
- **HTTP Method** (e.g., GET, POST)
- **Headers** (e.g., Authentication, Content-Type)
- **URL/Endpoint**
- **Query Parameters** (Optional)
- **Request Body** (Optional)
  - **Example:**
    ```http
    POST https://api.example.com/users
    Headers:
        Authorization: Bearer abc123
        Content-Type: application/json
    Body:
    {
        "name": "John Doe",
        "email": "john@example.com"
    }
    ```

### Response Components
- **Status Code** (e.g., 200, 404)
- **Headers** (e.g., Content-Type, Cache-Control)
- **Response Body**
  - **Example:**
    ```http
    HTTP/1.1 201 Created
    Headers:
        Content-Type: application/json
    Body:
    {
        "id": 123,
        "name": "John Doe",
        "created_at": "2024-01-20T12:00:00Z"
    }
    ```

---

## Additional Topics
### Versioning in APIs
- URL Versioning: `/v1/resource`
- Header Versioning: `Accept: application/vnd.example.v1+json`

### Authentication and Authorization
- **OAuth 2.0**
- **JWT (JSON Web Tokens)**

### Error Handling and Status Codes
- `400 Bad Request`
- `401 Unauthorized`
- `500 Internal Server Error`

---

## Tools and Technologies
- **Postman** for testing.
- **Swagger** for documentation.
- **Curl** for command-line API interaction.

---
"""