# Hospital_Mngmnt-_securization
An Hospital management app, using Spring Framework's security.

# Spring Boot Security UserDetails Example

<!-- Add an actual screenshot of your application here -->
![Application Screenshot](<image_url>)

## Overview

**SpringBootSecurityUserDetails** is a Java EE web application developed using Spring MVC, Thymeleaf, and Spring Data JPA. The application manages patient data with features such as display, search, and deletion. It optimizes data manipulation through the use of Spring MVC and Spring Data JPA frameworks, with added security features provided by Spring Boot Security UserDetails.

## UserDetails Interface

`UserDetails` is an interface provided by Spring Security that represents user details, including authentication and authorization information. It contains essential user information such as username, password, authorities, and other relevant details required for authentication and access control.

## Project Structure

### 1. HospitalAppApplication

This code establishes initial roles and users, associating roles with users, possibly for testing or seeding a database on application startup.

<!-- Add an actual screenshot of HospitalAppApplication code here -->
![HospitalAppApplication Code](<image_url>)

### 2. SecurityController

This controller handles two endpoints: "/notAuthorized" and "/login".

#### 2.1. Login Endpoint

<!-- Add an actual screenshot of the login endpoint here -->
![Login Endpoint](<image_url>)

#### 2.2. Not Authorized Endpoint

<!-- Add an actual screenshot of the notAuthorized endpoint here -->
![Not Authorized Endpoint](<image_url>)

### 3. Security Package

A new package named 'entities' has been introduced to the project. This package includes classes like `AppRole` and `AppUser`, along with repositories (`AppRoleRepository` and `AppUserRepository`). The service layer includes an interface named `AccountService` and its implementation, `AccountServiceImpl`. Additionally, the class `UserDetailServiceImpl` implements the `UserDetails` interface.

<!-- Add an actual screenshot of the Security Package code here -->
![Security Package Code](<image_url>)

### 4. SecurityConfig

The `SecurityConfig` class sets up a `JdbcUserDetailsManager` bean for managing user details stored in a JDBC database. It configures security settings using `HttpSecurity`, including form-based authentication, resource access, and access denial handling.

<!-- Add an actual screenshot of the SecurityConfig code here -->
![SecurityConfig Code](<image_url>)

### 5. AppRole

The `AppRole` class represents a role in the application, utilizing annotations and Lombok features for concise code generation.

<!-- Add an actual screenshot of the AppRole code here -->
![AppRole Code](<image_url>)

### 6. AppUser

The `AppUser` class is a JPA entity representing a user, using Lombok annotations for concise code generation. It includes fields for user details such as userId, username, password, email, and a list of roles associated with the user through a Many-to-Many relationship.

<!-- Add an actual screenshot of the AppUser code here -->
![AppUser Code](<image_url>)

### 7. Repositories and Services

This section includes interfaces and services related to user and role management.

#### 7.1. AppRoleRepository

This interface provides CRUD operations for managing `AppRole` entities in a Spring application.

<!-- Add an actual screenshot of the AppRoleRepository code here -->
![AppRoleRepository Code](<image_url>)

#### 7.2. AppUserRepository

The `AppUserRepository` is a Spring Data JPA repository interface for the `AppUser` entity, extending JpaRepository. It includes a custom query method, `findByUsername`, for retrieving an `AppUser` by their username from the underlying database.

<!-- Add an actual screenshot of the AppUserRepository code here -->
![AppUserRepository Code](<image_url>)

#### 7.3. AccountService

The `AccountService` provides functionalities for user and role management, including creation, association, disassociation, and loading user information by username.

<!-- Add an actual screenshot of the AccountService code here -->
![AccountService Code](<image_url>)

#### 7.4. AccountServiceImpl

The `AccountServiceImpl` class encapsulates the logic for user and role management, ensuring secure practices such as password encoding and transactional operations.

#### 7.5. UserDetailServiceImpl

The `UserDetailServiceImpl` class serves as a bridge between Spring Security's authentication mechanism and the application's user management system. It retrieves user details from the `AccountService` for authentication and authorization purposes.

## User Authentication Strategies

### 1. InMemoryUserDetailsManager

- Implementation of `UserDetailsManager` in Spring Security.
- Stores user details in memory.
- Suitable for small applications or testing.
- User details are not persistent and are lost on application restart.

### 2. JdbcUserDetailsManager

- Implementation of `UserDetailsManager` in Spring Security.
- Stores user details in a relational database using JDBC.
- Suitable for larger applications where user details need to be persistent.
- User details are stored in database tables.

### 3. UserDetails Interface

- Interface in Spring Security representing user details.
- Contains information like username, password, authorities (roles), account status, etc.
- Implemented by objects that hold user details, and both `InMemoryUserDetailsManager` and `JdbcUserDetailsManager` work with `UserDetails` objects.

In essence, these components provide different ways of managing user details, either in-memory or through a JDBC-connected database, catering to different application needs and scales.

## User Interfaces

### 1. Admin Interface

<!-- Add an actual screenshot of the admin interface here -->
![Admin Interface](<image_url>)

### 2. User Interface

<!-- Add an actual screenshot of the user interface here -->
![User Interface](<image_url>)
