# CS665_PROJECT1_GROUP_24 -  Hotel Management System

## Overview

The Hotel Management System is a database management system (DBMS) project designed to efficiently manage hotel-related operations. It consists of two main modules: Admin and Customer, each providing distinct functionalities for CRUD (Create, Read, Update, Delete) operations. We have used SQLite3 as our database, Python Django backend, Materialize CSS and HTML frontend, Git version control.

## Modules

### 1. Admin Module

#### Features
- **View Profile:** Admin can view and update their profile information.
- **Add/Delete Rooms:** Admin can add new rooms to the system or delete existing ones.
- **Check Room Availability:** Admin can check the availability of rooms for a specific date range.
- **View Reservations:** Admin can view all reservations made by customers.
  
### 2. Customer Module

#### Features
- **View Profile:** Customers can view and update their profile information.
- **Create Reservation:** Customers can create new reservations by selecting room type and specifying the date range.
- **View Receipts:** Customers can view receipts for their past reservations.
- **Check Room Availability:** Customers can check the availability of rooms for a specific date range.
- **Add Additional Services:** Customers can add additional services along with their reservation.
  
## Getting Started

### Prerequisites
- [Python](https://www.python.org/)
- [Django](https://www.djangoproject.com/)
- [Materialize CSS](https://materializecss.com/)

### Installation
1. Clone the repository: `git clone https://github.com/your-username/hotel-management-system.git`
2. Navigate to the project directory: `cd hotel-management-system`

### Database Schema
Our database consists of various tables each with Primary Key, Indexes, Foreign key and triggers. Main tables are mentioned in our db_description.

### Frontend 
The front-end of the Hotel Management System is built using HTML and styled with Materialize CSS framework, providing an intuitive and visually appealing user interface. Materialize CSS ensures responsiveness and a modern design, enhancing the user experience for both administrators and customers.

### Backend
The back-end of the Hotel Management System is powered by the Python Django framework. Django offers a robust and scalable architecture for handling server-side logic, managing databases, and processing user requests. The backend includes models for User, Profile, Room, Reservation, and Receipt, which are responsible for defining the database structure and handling CRUD operations.

The SQLite database is utilized for data storage, providing a lightweight and easy-to-use solution for development. Database migrations are managed through Django's built-in migration system.

## Project Execution and Explanation Video:

- https://youtu.be/yJwaHcU3Qhw

## PROJECT REPO
- https://github.com/LavanyaPasumarthi71/CS665_PROJECT1_GROUP_24

## Contributions

- Lavanya Pasumarthi (GITHUB ID - LavanyaPasumarthi71 -WSU ID - C788P474) - Responsible for designing the database schema.Implemented the structure and relationships between different entities.Also responisble to add database connections and backend and UI design of applications.
- Gunturi Venkata Reddy (GITHUB ID - VenkataReddyGUnturi1 -  WSU ID - J486Z329) -Tasked with inserting data into the database.Assisted in performing CRUD (Create, Read, Update, Delete) operations.Also did perform backend and frontend binding logic.
- Chandra Kiran danda (GITHUB ID - kirandanda2001 - WSU ID - X894M838)- Focused on implementing CRUD operations on the data.Ensured smooth functionality for creating, reading, updating, and deleting records.And helped in performing UI logic for the application and tested application thoroughly.

