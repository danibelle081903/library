# Library Management API

A lightweight API for managing users, authors, books, and authentication using PHP and the Slim framework. It features secure JSON Web Token (JWT) authentication and token management for streamlined operations.

## Features

- **User Management:** Register, Authenticate, Show, Update, Delete  
- **Author Management:** Register, Show, Update, Delete  
- **Book Management:** Register, Show, Update, Delete  
- **Books Authors Management:** Register, Show, Update, Delete  
- **Token Management:** Generate, Validate, Mark as Used  

## Prerequisites

- PHP 7.4 or higher  
- Composer  
- MySQL  

## Installation

### 1. Clone the Repository

```bash
git clone https://github.com/danibelle081903/library.git
cd library-management-api
```

### 2. Install Dependencies

```bash
composer install
```

### 3. Configure Database Connection

Update the database connection details in `index.php`:

```php
<?php
$servername = "localhost";
$username = "root";
$password = "";
$dbname = "library";
?>
```

## Usage

### User Management

#### Register Users
- **Endpoint:** `/user/register`  
- **Method:** `POST`  
- **Payload:**
  ```json
  {
    "username": "your_username",
    "password": "your_password"
  }
  ```

#### Authenticate Users
- **Endpoint:** `/user/auth`  
- **Method:** `POST`  
- **Payload:**
  ```json
  {
    "username": "your_username",
    "password": "your_password"
  }
  ```

#### Show Users
- **Endpoint:** `/user/show`  
- **Method:** `GET`  
- **Headers:**
  ```json
  {
    "Authorization": "Bearer your_token"
  }
  ```

#### Update Users
- **Endpoint:** `/user/update`  
- **Method:** `PUT`  
- **Payload:**
  ```json
  {
    "token": "your_token",
    "userid": "your_userid",
    "username": "your_new_username",
    "password": "your_new_password"
  }
  ```

#### Delete Users
- **Endpoint:** `/user/delete`  
- **Method:** `DELETE`  
- **Payload:**
  ```json
  {
    "token": "your_token",
    "userid": "your_userid"
  }
  ```

### Author Management

#### Register Author
- **Endpoint:** `/author/register`  
- **Method:** `POST`  
- **Payload:**
  ```json
  {
    "token": "your_token",
    "name": "author_name"
  }
  ```

#### Show Authors
- **Endpoint:** `/author/show`  
- **Method:** `GET`  
- **Headers:**
  ```json
  {
    "Authorization": "Bearer your_token"
  }
  ```

#### Update Author
- **Endpoint:** `/author/update`  
- **Method:** `PUT`  
- **Payload:**
  ```json
  {
    "token": "your_token",
    "authorid": "author_id",
    "name": "new_author_name"
  }
  ```

#### Delete Author
- **Endpoint:** `/author/delete`  
- **Method:** `DELETE`  
- **Payload:**
  ```json
  {
    "token": "your_token",
    "authorid": "author_id"
  }
  ```

### Book Management

#### Register Book
- **Endpoint:** `/book/register`  
- **Method:** `POST`  
- **Payload:**
  ```json
  {
    "token": "your_token",
    "title": "book_title",
    "authorid": 1
  }
  ```

#### Show Books
- **Endpoint:** `/book/show`  
- **Method:** `GET`  
- **Headers:**
  ```json
  {
    "Authorization": "Bearer your_token"
  }
  ```

#### Update Book
- **Endpoint:** `/book/update`  
- **Method:** `PUT`  
- **Payload:**
  ```json
  {
    "token": "your_token",
    "bookid": 1,
    "title": "new_book_title",
    "authorid": 1
  }
  ```

#### Delete Book
- **Endpoint:** `/book/delete`  
- **Method:** `DELETE`  
- **Payload:**
  ```json
  {
    "token": "your_token",
    "bookid": 1
  }
  ```

#### Register Book Author
- **Endpoint:** `/book_author/register`  
- **Method:** `POST`  
- **Payload:**

```json
{
  "token": "your_token",
  "bookid": 1,
  "authorid": 1
}
```

#### Show Book Authors
- **Endpoint:** `/book_author/show`  
- **Method:** `GET`  
- **Headers:**

```json
{
  "Authorization": "Bearer your_token"
}
```

#### Update Book Author
- **Endpoint:** `/book_author/update`  
- **Method:** `PUT`  
- **Payload:**

```json
{
  "token": "your_token",
  "collectionid": 1,
  "bookid": 1,
  "authorid": 1
}
```

#### Delete Book Author
- **Endpoint:** `/book_author/delete`  
- **Method:** `DELETE`  
- **Payload:**

```json
{
  "token": "your_token",
  "collectionid": 1
}
``` 

### Token Management

- Tokens are generated during authentication and stored in the `tokens` table.  
- Tokens can be validated and revoked using the provided endpoints and helper functions.

## License

This project is licensed under the MIT License. See the `LICENSE` file for details.

---
