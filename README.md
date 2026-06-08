# Financial Advisor Management System - Data Model Implementation

## Overview

This project implements the data model for a Financial Advisor Management System using Spring Boot and the Java Persistence API (JPA).

The application enables financial advisors to manage clients, portfolios, and securities through a relational database-backed system. The primary objective of this task was to convert the Entity Relationship Diagram (ERD) designed in Task 1 into fully functional JPA entity classes.

---

## Features

* Manage Financial Advisors
* Manage Clients
* Maintain Client Portfolios
* Track Securities within Portfolios
* Object-Relational Mapping using JPA
* Relational Database Integration
* Spring Boot Backend Architecture

---

## Technology Stack

* Java
* Spring Boot
* Spring Data JPA
* Hibernate ORM
* Maven
* Relational Database (MySQL/H2)
* IntelliJ IDEA
* Git & GitHub

---

## Data Model

### Financial Advisor

Stores advisor information and manages multiple clients.

Attributes:

* advisorId
* firstName
* lastName
* email
* phoneNumber

Relationship:

* One Financial Advisor can manage many Clients.

---

### Client

Stores client information.

Attributes:

* clientId
* firstName
* lastName
* email
* phoneNumber

Relationship:

* Many Clients belong to one Financial Advisor.
* One Client owns one Portfolio.

---

### Portfolio

Represents a client's investment portfolio.

Attributes:

* portfolioId
* portfolioName

Relationship:

* One Portfolio belongs to one Client.
* One Portfolio contains multiple Securities.

---

### Security

Represents an investment held within a portfolio.

Attributes:

* securityId
* securityName
* category
* purchaseDate
* purchasePrice
* quantity

Relationship:

* Many Securities belong to one Portfolio.

---

## Entity Relationships

```text
FinancialAdvisor
        |
        | 1 : M
        |
      Client
        |
        | 1 : 1
        |
    Portfolio
        |
        | 1 : M
        |
     Security
```

---

## JPA Relationships Used

| Relationship              | Annotation |
| ------------------------- | ---------- |
| FinancialAdvisor → Client | @OneToMany |
| Client → FinancialAdvisor | @ManyToOne |
| Client → Portfolio        | @OneToOne  |
| Portfolio → Security      | @OneToMany |
| Security → Portfolio      | @ManyToOne |

---

## Project Structure

```text
src
 └── main
     └── java
         └── com.example.financialadvisor
             ├── entities
             │   ├── FinancialAdvisor.java
             │   ├── Client.java
             │   ├── Portfolio.java
             │   └── Security.java
             ├── repository
             ├── service
             └── controller
```

---

## Key Implementation Details

* All entities are annotated with `@Entity`.
* Primary keys use `@Id` and `@GeneratedValue`.
* Relationships are mapped using JPA relationship annotations.
* Constructors initialize all instance variables.
* Getters and setters are provided for all fields.
* Foreign key relationships are maintained using `@JoinColumn`.

---

## Learning Outcomes

Through this project, I gained hands-on experience with:

* Entity Relationship Modeling
* Spring Boot Development
* Java Persistence API (JPA)
* Hibernate ORM
* Database Normalization
* Object-Relational Mapping
* One-to-One Relationships
* One-to-Many Relationships
* Relational Database Design
* Git and GitHub Version Control

---

## Future Enhancements

* REST API implementation
* Authentication and Authorization
* Portfolio Analytics Dashboard
* Security Performance Tracking
* Automated Portfolio Valuation
* Cloud Deployment

---

## Author

Rajiv Pillalamarri

---

## License

This project was developed as part of a software engineering job simulation and is intended for educational purposes.
