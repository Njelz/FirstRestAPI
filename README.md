Task 2 – Spring Boot REST API Application


Project Overview

This project is a REST API backend application created using Spring Initializr in IntelliJ. It allows users to perform full CRUD operations for managing products, utilising an H2 In-Memory Database for data persistence and Spring Data JPA for database interaction.

 

Technologies Used:

•Java 17: The main programming language

•Spring Boot DevTools: To set up the application and REST controllers

•Spring Data JPA: To handle database operations without writing complex SQL

•Spring Web: Used to handle HTTP requests

•H2 Database: An in-memory database used for testing and development

•Maven: Used for dependency management and building the project

•Postman & Swagger: To test all the API endpoints and verify the responses.

 

Project Structure:

FirstRestAPI
├── src
│   ├── main
│   │   ├── java
│   │   │   └── pl.edu.vistula.firstrestapi
│   │   │       ├── FirstRestApiApplication.java
│   │   │       └── product
│   │   │           ├── api
│   │   │           │   ├── request (ProductRequest, UpdateProductRequest)
│   │   │           │   ├── response (ProductResponse)
│   │   │           │   └── ProductController.java
│   │   │           ├── domain
│   │   │           │   └── Product.java
│   │   │           ├── repository
│   │   │           │   ├── oldProductRepository.java
│   │   │           │   └── ProductRepository.java
│   │   │           ├── service
│   │   │           │   └── ProductService.java
│   │   │           └── support
│   │   │               ├── exception (ProductNotFoundException)
│   │   │               ├── ProductExceptionAdvisor.java
│   │   │               ├── ProductExceptionSupplier.java
│   │   │               └── ProductMapper.java
│   │   └── resources
│   │       └── application.properties
├── screenshots
├── .gitignore
├── pom.xml
└── README.md

The project follows a Domain-Driven Design(DDD) approach, where all components related to the Product domain are grouped.

Task 2G
