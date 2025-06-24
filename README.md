# Airbnb Clone Project

## Overview
The Airbnb Clone Project is a full-stack web application designed to simulate a robust booking platform similar to Airbnb. This project focuses on backend development, database design, API creation, and application security, providing a comprehensive learning experience in building scalable and secure web applications.

## Project Goals
- Implement secure user management including registration and authentication.
- Develop property listing features with CRUD operations.
- Create a booking system to manage reservations.
- Integrate payment processing for handling transactions.
- Enable users to post reviews and ratings.
- Optimize database performance with indexing and caching.
- Document APIs using OpenAPI and support flexible querying with GraphQL.
- Establish CI/CD pipelines for automated testing and deployment.

## Technology Stack
- **Backend Framework:** Django, Django REST Framework
- **Database:** PostgreSQL
- **API Query Language:** GraphQL
- **Asynchronous Tasks:** Celery
- **Caching & Session Management:** Redis
- **Containerization:** Docker
- **CI/CD:** GitHub Actions or similar platforms

---
## Technology Stack Description

- **Django:** A high-level Python web framework used for building the backend RESTful APIs, handling business logic, and managing server-side operations.

- **Django REST Framework:** An extension of Django that simplifies the creation of RESTful APIs, providing tools for serialization, authentication, and viewsets.

- **PostgreSQL:** A powerful, open-source relational database system used to store and manage the application's data securely and efficiently.

- **GraphQL:** A flexible query language for APIs that allows clients to request exactly the data they need, improving efficiency over traditional REST endpoints.

- **Celery:** An asynchronous task queue used to handle background tasks such as sending notifications and processing payments without blocking the main application flow.

- **Redis:** An in-memory data store used for caching frequently accessed data and managing user sessions to improve application performance.

- **Docker:** A containerization platform that ensures consistent development and deployment environments across different machines.

- **CI/CD Pipelines (e.g., GitHub Actions):** Automated workflows that build, test, and deploy code changes, enhancing development efficiency and reducing errors.

---

## Team Roles

### Backend Developer
Responsible for designing, implementing, and maintaining the server-side logic of the application. This includes creating API endpoints, managing business logic, and ensuring secure and efficient data processing.

### Database Administrator (DBA)
Manages the design, implementation, and maintenance of the database systems. Responsibilities include optimizing queries, indexing, ensuring data integrity, backup, and recovery.

### DevOps Engineer
Handles deployment, monitoring, and scaling of backend services. Implements CI/CD pipelines, manages containerization (e.g., Docker), and ensures the infrastructure is reliable and secure.

### QA Engineer
Ensures the backend functionalities meet quality standards through rigorous testing. Designs test cases, performs automated and manual testing, and verifies bug fixes and feature implementations.

---
## Database Design

### Key Entities and Their Fields

#### Users
- `id` (Primary Key): Unique identifier for each user.
- `username`: User’s login name.
- `email`: User’s email address.
- `password_hash`: Hashed password for authentication.
- `profile_info`: Additional profile details such as name, bio, and photo.

#### Properties
- `id` (Primary Key): Unique identifier for each property.
- `owner_id` (Foreign Key): References the user who owns the property.
- `title`: Title or name of the property.
- `description`: Detailed description of the property.
- `location`: Address or geographic coordinates.
- `price_per_night`: Cost of renting the property per night.

#### Bookings
- `id` (Primary Key): Unique identifier for each booking.
- `user_id` (Foreign Key): References the user who made the booking.
- `property_id` (Foreign Key): References the booked property.
- `check_in_date`: Start date of the booking.
- `check_out_date`: End date of the booking.
- `status`: Current status (e.g., confirmed, cancelled).

#### Reviews
- `id` (Primary Key): Unique identifier for each review.
- `user_id` (Foreign Key): References the user who wrote the review.
- `property_id` (Foreign Key): References the reviewed property.
- `rating`: Numeric rating (e.g., 1 to 5 stars).
- `comment`: Textual feedback from the user.
- `created_at`: Timestamp of when the review was posted.

#### Payments
- `id` (Primary Key): Unique identifier for each payment.
- `booking_id` (Foreign Key): References the related booking.
- `amount`: Payment amount.
- `payment_date`: Date when the payment was made.
- `payment_status`: Status of the payment (e.g., completed, pending).

### Relationships Between Entities
- A **User** can own multiple **Properties** (one-to-many).
- A **User** can make multiple **Bookings** (one-to-many).
- Each **Booking** is linked to one **Property** (many-to-one).
- **Reviews** are written by **Users** for **Properties** (many-to-many relationship via Reviews).
- Each **Payment** is associated with one **Booking** (one-to-one or one-to-many depending on payment installments).

---



This repository will serve as the foundation for building and maintaining the backend services of the Airbnb Clone application.

