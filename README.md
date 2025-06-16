# Airbnb Clone Project

## 🚀 Project Overview

The Airbnb Clone Project is a backend-focused application that simulates the core functionalities of the Airbnb platform. It provides a robust, scalable system for handling user registration, property listings, bookings, payments, and reviews.

This project is designed to deepen your knowledge of backend development, database design, API development, and software deployment practices in a real-world team environment.

## 🏆 Project Goals

- **User Management**: Secure registration, login, and profile management.
- **Property Listings**: Create, update, retrieve, and delete properties.
- **Booking System**: Allow users to book and manage property reservations.
- **Payment Processing**: Integrate payment features for handling transactions.
- **Review System**: Enable users to post and manage property reviews.
- **Data Optimization**: Implement indexing and caching for performance.

## ⚙️ Technology Stack

Below is a breakdown of the technologies used in this project and their specific roles:

### 🔹 Django
A high-level Python web framework used for building and structuring the backend of the application. It handles routing, request processing, and business logic implementation.

### 🔹 Django REST Framework (DRF)
An extension for Django that simplifies the creation of RESTful APIs. It provides tools for serialization, authentication, and standard HTTP method support (GET, POST, PUT, DELETE).

### 🔹 PostgreSQL
A robust, open-source relational database used to store all persistent data such as user details, property listings, bookings, payments, and reviews.

### 🔹 GraphQL
A query language for APIs that allows clients to request exactly the data they need. It provides a more efficient and flexible alternative to REST for specific use cases.

### 🔹 Celery
An asynchronous task queue used for running background tasks, such as sending confirmation emails, processing payments, or generating reports.

### 🔹 Redis
An in-memory data store used alongside Celery to manage task queues, and also as a caching layer to enhance performance and reduce database load.

### 🔹 Docker
A containerization platform that packages the project and its dependencies into isolated environments. This ensures consistent development, testing, and production environments.

### 🔹 GitHub Actions (CI/CD)
A tool used to automate testing, linting, and deployment of the application whenever code changes are pushed to the repository.

---



## 👥 Team Roles

In this project, multiple specialized roles work collaboratively to ensure successful delivery of the Airbnb Clone backend. Below are the core team roles and their responsibilities:

### 🔧 Backend Developer
- Implements the RESTful and GraphQL API endpoints.
- Develops business logic for user authentication, property management, bookings, and payments.
- Ensures code is modular, maintainable, and testable.

### 🛢️ Database Administrator (DBA)
- Designs and manages the PostgreSQL database schema.
- Optimizes database performance through indexing and query tuning.
- Ensures data integrity, backup strategies, and availability.

### 🚀 DevOps Engineer
- Sets up and manages CI/CD pipelines using GitHub Actions or similar tools.
- Configures Docker environments for development and deployment.
- Monitors server uptime and ensures scalability and security in deployment.

### ✅ QA Engineer
- Develops and runs test plans to verify backend functionality.
- Automates API testing and ensures endpoints meet expected behavior.
- Reports and tracks bugs, ensuring issues are resolved before deployment.

### 📄 Technical Writer / Documentation Specialist (Optional Role)
- Maintains up-to-date and developer-friendly documentation.
- Writes detailed API specs (OpenAPI), architecture guides, and setup instructions.
- Ensures documentation supports onboarding and third-party integrations.

---

## 📁 Repository Structure

- `README.md` – Project documentation and overview
- `backend/` – Django project and apps
- `docker/` – Docker configuration files
- `.github/workflows/` – CI/CD pipeline configurations

---

## 🗃️ Database Design

The database for the Airbnb Clone project is structured around several core entities. These entities represent the key components of the application and are related to one another to reflect real-world business logic.

### 🧑 Users
Represents the people using the platform, including guests and hosts.

**Key Fields:**
- `id`: Unique identifier for each user
- `name`: Full name of the user
- `email`: Used for authentication and communication
- `password`: Encrypted password for login
- `is_host`: Boolean indicating whether the user is a host

**Relationships:**
- A user can list multiple properties.
- A user can make multiple bookings.
- A user can leave multiple reviews.

---

### 🏠 Properties
Represents the listings created by hosts.

**Key Fields:**
- `id`: Unique identifier for each property
- `title`: Name of the listing
- `description`: Details about the property
- `location`: Address or city of the property
- `price_per_night`: Cost to book per night
- `owner_id`: Foreign key referencing the user who owns the property

**Relationships:**
- Each property is owned by one user (host).
- A property can have many bookings.
- A property can have multiple reviews.

---

### 📅 Bookings
Captures reservations made by users for properties.

**Key Fields:**
- `id`: Unique identifier for each booking
- `user_id`: Foreign key referencing the user who made the booking
- `property_id`: Foreign key referencing the booked property
- `check_in`: Date of check-in
- `check_out`: Date of check-out

**Relationships:**
- Each booking is made by one user and for one property.

---

### 💳 Payments
Tracks payments associated with bookings.

**Key Fields:**
- `id`: Unique identifier for each payment
- `booking_id`: Foreign key referencing the related booking
- `amount`: Total amount paid
- `payment_date`: Date the payment was processed
- `payment_status`: Status (e.g., completed, pending)

**Relationships:**
- Each payment is linked to a single booking.

---

### ⭐ Reviews
Stores feedback submitted by users for properties.

**Key Fields:**
- `id`: Unique identifier for each review
- `user_id`: Foreign key referencing the user who wrote the review
- `property_id`: Foreign key referencing the reviewed property
- `rating`: Numerical rating (e.g., 1–5 stars)
- `comment`: Textual review content

**Relationships:**
- Each review is written by one user for one property.

---

### 🔗 Entity Relationships Summary

- A **User** can:
  - Own multiple **Properties**
  - Make multiple **Bookings**
  - Write multiple **Reviews**

- A **Property** can:
  - Be booked many times via **Bookings**
  - Receive multiple **Reviews**

- A **Booking** is:
  - Made by one **User**
  - Linked to one **Property**
  - Has one related **Payment**

- A **Review** is:
  - Written by a **User**
  - Belongs to a **Property**


> 💡 **Note**: This project is an excellent opportunity to practice professional software development workflows, API security, and collaborative project execution.

