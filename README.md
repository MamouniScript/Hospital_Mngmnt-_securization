# Hospital_Mngmnt-_securization
An Hospital management app, using Spring Framework's security.


## Overview

Secured Hospital management app is a Java EE web application developed using Spring MVC, Thymeleaf, and Spring Data JPA. The application manages patient data with features such as display, search, and deletion. It optimizes data manipulation through the use of Spring MVC and Spring Data JPA frameworks, with added security features provided by Spring Boot Security UserDetails.

## UserDetails Interface

`UserDetails` is an interface provided by Spring Security that represents user details, including authentication and authorization information. It contains essential user information such as username, password, authorities, and other relevant details required for authentication and access control.

## Project Structure

### 1. HospitalAppApplication

This code establishes initial roles and users, associating roles with users, possibly for testing or seeding a database on application startup.

### 2. SecurityController

This controller handles two endpoints: "/notAuthorized" and "/login".

#### 2.1. Login Endpoint


#### 2.2. Not Authorized Endpoint


### 3. Security Package

A new package named 'entities' has been introduced to the project. This package includes classes like `AppRole` and `AppUser`, along with repositories (`AppRoleRepository` and `AppUserRepository`). The service layer includes an interface named `AccountService` and its implementation, `AccountServiceImpl`. Additionally, the class `UserDetailServiceImpl` implements the `UserDetails` interface.


### 4. SecurityConfig

The `SecurityConfig` class sets up a `JdbcUserDetailsManager` bean for managing user details stored in a JDBC database. It configures security settings using `HttpSecurity`, including form-based authentication, resource access, and access denial handling.


### 5. AppRole

The `AppRole` class represents a role in the application, utilizing annotations and Lombok features for concise code generation.


### 6. AppUser

The `AppUser` class is a JPA entity representing a user, using Lombok annotations for concise code generation. It includes fields for user details such as userId, username, password, email, and a list of roles associated with the user through a Many-to-Many relationship.


### 7. Repositories and Services

This section includes interfaces and services related to user and role management.

#### 7.1. AppRoleRepository

This interface provides CRUD operations for managing `AppRole` entities in a Spring application.


#### 7.2. AppUserRepository

The `AppUserRepository` is a Spring Data JPA repository interface for the `AppUser` entity, extending JpaRepository. It includes a custom query method, `findByUsername`, for retrieving an `AppUser` by their username from the underlying database.


#### 7.3. AccountService

The `AccountService` provides functionalities for user and role management, including creation, association, disassociation, and loading user information by username.


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

### After running the app beside having a running MySQL server also, the app should be available at http://localhost:8080 
