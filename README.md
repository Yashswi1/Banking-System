# Banking Management System

A console-based Banking Management System developed using **Java, JDBC, and MySQL**. This application allows users to register, log in, create bank accounts, and perform basic banking operations through a menu-driven interface.

## Features

- **User Registration:** Register using full name, email, and password.
- **User Login:** Authenticate users using email and password.
- **Account Creation:** Create a bank account with an automatically generated account number.
- **Debit Money:** Withdraw money after security PIN verification and balance validation.
- **Credit Money:** Deposit money into an account.
- **Money Transfer:** Transfer funds between two bank accounts.
- **Check Balance:** View account balance after security PIN verification.
- **Transaction Management:** Uses JDBC transactions with commit and rollback.

## Technologies Used

- Java
- JDBC (Java Database Connectivity)
- MySQL
- MySQL Connector/J
- IntelliJ IDEA

## Project Structure

```text
BankingSystem/
│
├── src/
│   └── BankingManagementSystem/
│       ├── BankingApp.java
│       ├── User.java
│       ├── Accounts.java
│       └── AccountManager.java
│
├── .gitignore
└── BankingSystem.iml
```

## Database Setup

1. Open MySQL Workbench or your MySQL terminal.
2. Create the database:

```sql
CREATE DATABASE banking_system;
USE banking_system;
```

3. Create the User table:

```sql
CREATE TABLE User (
    full_name VARCHAR(100),
    email VARCHAR(100) PRIMARY KEY,
    password VARCHAR(255)
);
```

4. Create the Accounts table:

```sql
CREATE TABLE Accounts (
    account_number BIGINT PRIMARY KEY,
    full_name VARCHAR(100),
    email VARCHAR(100) UNIQUE,
    balance DECIMAL(10,2),
    security_pin CHAR(4)
);
```

**Note:** These table definitions are based on the columns used by the Java code. They are suggested setup schemas, not an exported database schema.

## Configuration

Update the database connection settings in `BankingApp.java`:

```java
private static final String url =
    "jdbc:mysql://localhost:3306/banking_system";

private static final String username = "root";

// Configure your database password securely.
```

Add MySQL Connector/J to your project dependencies.

For better security, use environment variables for database credentials instead of hardcoding passwords.

## How to Run

1. Clone this repository:

```bash
git clone https://github.com/Yashswi1/Banking-System.git
```

2. Open the project in IntelliJ IDEA.
3. Configure MySQL and create the database and tables.
4. Add MySQL Connector/J to the project.
5. Configure your database connection.
6. Open `BankingApp.java`.
7. Run the `main()` method.

## Application Menu

```text
*** WELCOME TO BANKING SYSTEM ***

1. Register
2. Login
3. Exit
```

After successful login:

```text
1. Debit Money
2. Credit Money
3. Transfer Money
4. Check Balance
5. Log Out
```

## Learning Outcomes

This project demonstrates practical implementation of:

- Object-Oriented Programming in Java.
- JDBC database connectivity.
- SQL queries using PreparedStatement.
- User authentication.
- CRUD operations.
- Database transaction handling.
- Exception handling.

## Future Improvements

- Password hashing and secure authentication.
- Input validation and better error handling.
- Transaction history.
- Improved database constraints.
- GUI or web-based interface.

## Author

**Yashswi Soni**

GitHub: [Yashswi1](https://github.com/Yashswi1)

---

*This project was developed for learning Java, JDBC, MySQL, and backend development concepts.*
