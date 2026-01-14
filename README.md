# Task 2 – Spring Boot REST API Application

## Project Overview

This project is a REST API backend application created using Spring Initializr in IntelliJ. It allows users to perform full CRUD operations for managing products, utilising an H2 In-Memory Database for data persistence and Spring Data JPA for database interaction.

## Technologies Used:

•Java 17: The main programming language

•Spring Boot DevTools: To set up the application and REST controllers

•Spring Data JPA: To handle database operations without writing complex SQL

•Spring Web: Used to handle HTTP requests

•H2 Database: An in-memory database used for testing and development

•Maven: Used for dependency management and building the project

•Postman & Swagger: To test all the API endpoints and verify the responses.

## Project Structure:

<img width="267" height="287" alt="Screenshot 2026-01-12 132603" src="https://github.com/user-attachments/assets/fed8a0b1-6b13-49eb-b0c8-97d7703ae60c" />

The project follows a Domain-Driven Design(DDD) approach, where all components related to the Product domain are grouped.

### Layer Responsibilities:

•API Layer: Handles HTTP requests and responses using DTOs to keep the internal domain model private.

•Domain Layer: Contains the JPA entity (Product) which represents the database table.

•Repository Layer: An interface that extends JpaRepository to handle all database operations.

•Service Layer: Contains the business logic and coordinates between the API and Repository layers.

•Support Layer: Handles cross-cutting concerns like mapping between objects and global exception handling.

## Implementation & Testing Progress

The development of this project was documented through various stages of implementation and testing. Below is a detailed flow of how the application was built and verified.

## 1. Initial Setup and API Definition

The project started with setting up the Spring Boot environment and defining the initial API structure. I used Swagger to visualize the endpoints early on.

![First Post Test](screenshots/Screenshot_2026-01-03_213131.png).

   *First POST Test: Successfully created the first product entry.*

![Swagger Setup](screenshots/Screenshot_2026-01-03_222020.png)

   *Swagger UI: Verified the API documentation was being generated correctly.*

## 2. Incremental Development and Verification

As the service and repository layers were developed, I conducted multiple tests to ensure stability and accurate data retrieval.

![GET Test](screenshots/Screenshot_2026-01-04_232956.png)

   *GET by ID: Testing the retrieval of the first project entry.*
   
![Progress 1](screenshots/Screenshot_2026-01-05_193724.png)
![Progress 2](screenshots/Screenshot_2026-01-05_193946.png)
![Progress 3](screenshots/Screenshot_2026-01-05_194112.png)

   *Progress Checks: Multiple tests were run to ensure stability as the service layer was being built.*

## 3. Final CRUD Operations

I finalised the core CRUD operations using realistic data. This stage involved testing all HTTP methods to ensure full functionality.

![POST Laptop](screenshots/Screenshot_2026-01-06_144157.png)

   *Creating "Laptop"*

![GET All](screenshots/Screenshot_2026-01-06_144255.png)

   *Retrieving All Products*

![PUT Update](screenshots/Screenshot_2026-01-06_144417.png)

   *Updating to "Gaming Laptop"*

![DELETE Test](screenshots/Screenshot_2026-01-06_144520.png)

   *Deleting a Product*

![404 Error](screenshots/Screenshot_2026-01-06_144633.png)

   *Error Handling (404): Verified that the system correctly handles missing products.*

## 4. Database Tests

In this stage CRUD operations were performed to later verify the database functionality

![Validation 1](screenshots/Screenshot_2026-01-06_160905.png)
   *Initial H2 Console view*

![Validation 2](screenshots/Screenshot_2026-01-06_175753.png)
![Validation 3](screenshots/Screenshot_2026-01-06_175859.png)
![Validation 4](screenshots/Screenshot_2026-01-06_175920.png)
![Validation 5](screenshots/Screenshot_2026-01-06_175950.png)
![Validation 6](screenshots/Screenshot_2026-01-06_180022.png)
     *Inputs*

## 5. Database Verification

The final step was ensuring that all data was correctly reaching the H2 database.

![H2 Table](screenshots/Screenshot_2026-01-10_173313.png)
   *H2 Console Check: Verified the "PRODUCTS" table content.*

![H2 Update](screenshots/Screenshot_2026-01-10_173502.png)
   *PUT Verification: Confirmed updates are reflected in the database.*

![H2 Delete](screenshots/Screenshot_2026-01-10_173541.png)
   *DELETE Verification: Confirmed records are removed from the database.*

![H2 Final](screenshots/Screenshot_2026-01-10_173618.png)
   *Final Database*


# Task 2G Answer

The reason we can use methods like save() and findAll() despite our ProductRepository being empty is due to the way Spring Data JPA handles interfaces at runtime. By extending JpaRepository, our interface inherits a set of standard method signatures, and Spring automatically generates a concrete implementation for us using a mechanism called a Dynamic Proxy. This proxy delegates all our calls to a built-in class called SimpleJpaRepository, which contains the actual logic for interacting with the database. This powerful feature allows us to perform full CRUD operations without writing any boilerplate code, as Spring handles the implementation details for us behind the scenes.
