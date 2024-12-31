# Advanced Shopping Platform

## Overview
The Advanced Shopping Platform is a feature-rich web application designed to efficiently manage users and products. Built with Flask, this application provides robust features like user authentication, product management, and email notifications. The platform utilizes MySQL for its database and ensures secure authentication using JSON Web Tokens (JWT).

## Features

### User Authentication
- Registration and login functionality with JWT-based session management.
- Password hashing and validation for enhanced security.

### Product Management
- Add, view, and manage products.
- Pagination for seamless product listings.

### Email Notifications
- Send welcome emails upon user registration.
- Notify users via email when a new product is added.

## Tech Stack
- **Backend:** Flask
- **Database:** MySQL with SQLAlchemy ORM
- **Authentication:** JWT (JSON Web Tokens)
- **Email:** Flask-Mail
- **Environment Management:** python-dotenv
- **Frontend:** HTML/CSS (Bootstrap optional)

## Installation

### Prerequisites
- Python 3.x
- MySQL server

### Steps
1. Clone the repository:
   ```bash
   git clone https://github.com/your-username/Shopping_Platform.git
   ```
2. Navigate to the project directory:
   ```bash
   cd Shopping_Platform
   ```
3. Install the required dependencies:
   ```bash
   pip install -r requirements.txt
   ```
4. Set up environment variables using a `.env` file. Example:
   ```env
   FLASK_APP=app.py
   FLASK_ENV=development
   SECRET_KEY=your_secret_key
   MAIL_SERVER=smtp.example.com
   MAIL_PORT=587
   MAIL_USERNAME=your_email@example.com
   MAIL_PASSWORD=your_password
   MAIL_USE_TLS=True
   MAIL_USE_SSL=False
   DATABASE_URI=mysql+pymysql://username:password@localhost/db_name
   ```
5. Initialize the database:
   ```bash
   flask db init
   flask db migrate
   flask db upgrade
   ```
6. Run the application:
   ```bash
   flask run
   ```

## API Endpoints

### User Registration
- **Endpoint:** `/users`
- **Method:** POST
- **Request Body:**
  ```json
  {
    "firstName": "John",
    "lastName": "Doe",
    "username": "johndoe",
    "email": "john@example.com",
    "password": "Password123!",
    "confirm_password": "Password123!"
  }
  ```
- **Response:**
  ```json
  {
    "message": "User account created"
  }
  ```

### User Login
- **Endpoint:** `/login`
- **Method:** POST
- **Request Body:**
  ```json
  {
    "username": "johndoe",
    "password": "Password123!"
  }
  ```
- **Response:**
  ```json
  {
    "status": true,
    "message": "Login successful.",
    "access_token": "your_jwt_token"
  }
  ```

### Add Product
- **Endpoint:** `/products`
- **Method:** POST
- **Headers:** `Authorization: Bearer <your_jwt_token>`
- **Request Body:**
  ```json
  {
    "product_name": "Product Name",
    "description": "Product Description",
    "price": 29.99
  }
  ```
- **Response:**
  ```json
  {
    "message": "Product added"
  }
  ```

### Display Products
- **Endpoint:** `/products`
- **Method:** GET
- **Query Parameters:** `page`, `per_page`
- **Response:**
  ```json
  {
    "status": true,
    "data": [
      {
        "product_id": 1,
        "product_name": "Product Name",
        "description": "Product Description",
        "price": 29.99
      }
    ],
    "total": 10,
    "pages": 1,
    "current_page": 1,
    "per_page": 10
  }
  ```

## Contributing

1. Fork the repository.
2. Create a feature branch:
   ```bash
   git checkout -b feature/your-feature
   ```
3. Commit your changes:
   ```bash
   git commit -am 'Add some feature'
   ```
4. Push to the branch:
   ```bash
   git push origin feature/your-feature
   ```
5. Open a pull request.

## Contact
For any questions or feedback, please contact:

**Praveen Kumar A**
Email: [neevarp02082003@gmail.com](mailto:neevarp02082003@gmail.com)

