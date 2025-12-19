🎮 Video Game Store API

A RESTful E-Commerce API built with Java, Spring Boot, and MySQL that powers a Video Game Store.
This project allows users to browse video game products and categories, while administrators can securely manage inventory.

📌 Project Overview

The Video Game Store API supports:

Browsing video game products

Viewing product categories

Searching products with filters

Secure admin-only product and category management

RESTful endpoints tested using Insomnia

This project was completed as part of a backend capstone focused on API design, database integration, and debugging real-world issues.

🛠️ Technologies Used

Java

Spring Boot

Spring Security

MySQL

JDBC

Insomnia (API testing)

IntelliJ IDEA

🗄️ Database

Database Name: videogamestore

Tables:

products

categories

users

Admin and user accounts are pre-seeded for testing

🔐 Security & Roles

The API uses role-based access control:

Role	Permissions
USER	View products and categories
ADMIN	Create, update, and delete products and categories

Admin-only endpoints are protected using Spring Security.

📂 Phase 1 – Categories API
Implemented Endpoints
Method	Endpoint	Description	Access
GET	/categories	Get all categories	Public
GET	/categories/{id}	Get category by ID	Public
GET	/categories/{id}/products	Get products in a category	Public
POST	/categories	Create a category	Admin
PUT	/categories/{id}	Update a category	Admin
DELETE	/categories/{id}	Delete a category	Admin
Key Features

Categories stored in MySQL

DAO pattern for database access

Secure admin-only modifications

Cross-origin enabled for frontend use

🐞 Phase 2 – Bug Fixes & Improvements
✅ Bug 1: Product Search Issues

Fixed incorrect filtering logic

Supports:

Category

Min price

Max price

Subcategory

Multiple filters now work together correctly

✅ Bug 2: Product Duplication on Update

Problem:
Updating a product created duplicate rows in the database.

Cause:
The PUT endpoint was incorrectly calling create() instead of update().

Fix:

Corrected the PUT endpoint to call productDao.update(id, product)

Updates now modify existing records instead of inserting new ones

🧪 Testing with Insomnia

Insomnia was used to verify all API functionality.

What Was Tested

GET products and categories

Search filters

Admin-only access control

Product updates (no duplicates)

Error handling (404 / 403)

Example Test Flow

GET a product

PUT update price

PUT update description

GET all products

Confirm only one product exists (no duplicates)

▶️ Running the Project

Clone the repository

Open in IntelliJ

Configure MySQL and run the provided SQL script

Run the Spring Boot application

Access API at:

http://localhost:8080


Test endpoints using Insomnia

📈 What This Project Demonstrates

REST API design

Secure CRUD operations

Debugging real production-style bugs

SQL + JDBC integration

Clean separation of concerns (Controller / DAO / Model)

API testing with Insomnia

🚀 Future Improvements

Add frontend UI for the Video Game Store

Pagination for product listings

Product reviews and ratings

User order history

👤 Author

Sherman Turner-Robinson
Aspiring software developer with a passion for video games, backend development, and building real-world applications.