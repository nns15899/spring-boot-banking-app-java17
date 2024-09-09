# Banking App API

In this tutorial, we will learn how to build REST APIs for a simple Banking application using Spring Boot, Spring Data JPA (Hibernate), and MySQL database.

## Table of Contents

- [Introduction](#introduction)
- [Features](#features)
- [Technologies Used](#technologies-used)
- [Getting Started](#getting-started)
- [Prerequisites](#prerequisites)
- [Installation](#installation)
- [Usage](#usage)
- [API Endpoints](#api-endpoints)
- [Contributing](#contributing)
- [License](#license)

## Introduction

This project is a simple Banking App with basic functionalities:
- Creating a bank account
- Fetching account details
- Making a deposit
- Making a withdrawal

## Features

- RESTful APIs for banking operations
- Data persistence using MySQL and Spring Data JPA
- Simple and intuitive API design

## Technologies Used

- **Java 17**
- **Spring Boot**
- **Spring Data JPA (Hibernate)**
- **MySQL Database**
- **Maven** for dependency management

## Getting Started

Follow these instructions to set up the project locally.

### Prerequisites

- **Java 17** installed
- **Maven** installed
- **MySQL** installed
- **Git** installed

### Installation

1. **Clone the repository:**

    ```bash
    git clone https://github.com/<username>/<repository-name>.git
    cd <repository-name>
    ```

2. **Set up the database:**

    - Open MySQL Workbench.
    - Create a schema named `banking_app`.
    - (Optional) Create a user and grant privileges to the schema.

3. **Configure database connection:**

    Update the `application.properties` file with your MySQL credentials:

    ```properties
    spring.datasource.url=jdbc:mysql://localhost:3306/banking_app
    spring.datasource.username=your_db_username
    spring.datasource.password=your_db_password
    spring.datasource.driver-class-name=com.mysql.cj.jdbc.Driver
    spring.jpa.hibernate.ddl-auto=update
    spring.jpa.show-sql=true
    ```

4. **Build and run the application:**

    ```bash
    mvn clean install
    mvn spring-boot:run
    ```

5. **Access the API:**

    The application will be running at `http://localhost:8080`.

## Usage

Use tools like Postman or cURL to test the API endpoints.

### API Endpoints

- **Create a Bank Account**
    - **Endpoint:** `POST /api/accounts`
    - **Description:** Creates a new bank account.
    - **Request Body:**
      ```json
      {
        "accountHolderName": "John Doe",
        "initialDeposit": 500
      }
      ```
    - **Response:**
      ```json
      {
        "accountId": 1,
        "accountHolderName": "John Doe",
        "balance": 500
      }
      ```

- **Get Account Details**
    - **Endpoint:** `GET /api/accounts/{id}`
    - **Description:** Fetches the details of a specific bank account.
    - **Response:**
      ```json
      {
        "accountId": 1,
        "accountHolderName": "John Doe",
        "balance": 500
      }
      ```

- **Make a Deposit**
    - **Endpoint:** `POST /api/accounts/{id}/deposit`
    - **Description:** Deposits a specified amount into the bank account.
    - **Request Body:**
      ```json
      {
        "amount": 200
      }
      ```
    - **Response:**
      ```json
      {
        "accountId": 1,
        "accountHolderName": "John Doe",
        "balance": 700
      }
      ```

- **Make a Withdrawal**
    - **Endpoint:** `POST /api/accounts/{id}/withdraw`
    - **Description:** Withdraws a specified amount from the bank account.
    - **Request Body:**
      ```json
      {
        "amount": 100
      }
      ```
    - **Response:**
      ```json
      {
        "accountId": 1,
        "accountHolderName": "John Doe",
        "balance": 600
      }
      ```

## Contributing

Contributions are welcome! Please fork the repository and open a pull request with your changes.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
