# Online Loan Management System

A full-stack loan processing web application built as a team project using Java, JSP, MySQL, HTML, CSS, and JavaScript.

## What It Does
A digital loan management platform — customers apply for loans online, managers approve or reject, and customers track repayments.

## Tech Stack
- Backend: Java, JSP
- Frontend: HTML, CSS, JavaScript
- Database: MySQL
- Concepts: OOP, RBAC, Normalization, SIT

## Key Features
- Online loan application submission
- Manager approval / rejection workflow
- Repayment tracking and management
- Role-based access control (RBAC)
- Secure client and server-side validation
- Normalized MySQL database design

## Database Schema
CREATE TABLE users (
    user_id INT PRIMARY KEY AUTO_INCREMENT,
    name VARCHAR(100) NOT NULL,
    email VARCHAR(100) UNIQUE NOT NULL,
    role ENUM('customer', 'manager') NOT NULL
);

CREATE TABLE loan_applications (
    loan_id INT PRIMARY KEY AUTO_INCREMENT,
    user_id INT,
    amount DECIMAL(10,2) NOT NULL,
    status ENUM('pending', 'approved', 'rejected') DEFAULT 'pending',
    FOREIGN KEY (user_id) REFERENCES users(user_id)
);

CREATE TABLE repayments (
    repayment_id INT PRIMARY KEY AUTO_INCREMENT,
    loan_id INT,
    amount_paid DECIMAL(10,2) NOT NULL,
    FOREIGN KEY (loan_id) REFERENCES loan_applications(loan_id)
);

## Testing
- Unit test cases for all modules
- System Integration Testing (SIT)
- Complete test documentation

## Academic Context
Degree: Master of Computer Applications (MCA)
University: Sri Venkateswara University, Tirupati
Type: Team Mini Project
Year: 2024

## Author
V. Roheth Naidu
MCA Graduate | Java Developer | AWS Cloud
LinkedIn: linkedin.com/in/roheth-naidu
Email: rohethnaidu@gmail.com
