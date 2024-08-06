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



Certainly! Here’s a detailed documentation for your Employee List page:

---

### Employee List Page Documentation

#### Overview
The Employee List page provides a comprehensive list of all employees. Users can perform various actions such as viewing profiles, editing employee positions, and exporting employee data. The available actions and functionalities are based on user roles.

#### Features and Functionalities

1. **Employee List**
   - Displays a list of employees with relevant information such as name, position, and department.
   - Includes pagination for easy navigation through large datasets.

2. **Actions**
   - **View Profile**
     - Allows users to view detailed profiles of individual employees.
     - Accessible by clicking on the "View Profile" button next to each employee's entry.
   - **Edit Employee Position**
     - Enables users to edit the position details of employees.
     - Accessible by clicking on the "Edit" button next to each employee's entry.
     - Changes are role-based and can be restricted to certain user roles (e.g., HR managers, supervisors).
   - **Batch Export**
     - Provides functionality to export the employee list to CSV or JSON formats.
     - Export options include full export or filtered export based on applied filters.
     - Export permissions are role-based, ensuring that only authorized users can perform export actions.

#### Role-Based Access
- **Administrator**
  - Full access to all functionalities including viewing profiles, editing positions, and exporting data.
- **HR Manager**
  - Can view profiles, edit positions, and export data.
- **Supervisor**
  - Can view profiles and edit positions.
- **Employee**
  - Limited to viewing profiles only.

#### Export Functionality
- Users with the necessary permissions can export the employee list.
- Export options:
  - **CSV Format**
    - Suitable for spreadsheet applications.
    - Includes all visible columns in the employee list.
  - **JSON Format**
    - Suitable for data interchange and integration with other systems.
    - Includes detailed employee information.

#### Usage Instructions

1. **Viewing Profiles**
   - Navigate to the Employee List page.
   - Click the "View Profile" button next to the desired employee’s entry to view detailed information.

2. **Editing Employee Positions**
   - Navigate to the Employee List page.
   - Click the "Edit" button next to the desired employee’s entry.
   - Make the necessary changes to the employee's position and save.

3. **Exporting Employee Data**
   - Navigate to the Employee List page.
   - Click the "Export" button.
   - Select the desired format (CSV or JSON) for the export.
   - Confirm the export action. The file will be downloaded based on the selected format and applied filters.

#### Notes
- Ensure you have the appropriate permissions for the actions you intend to perform.
- For any issues or further assistance, contact the system administrator.

---

This documentation provides a clear and detailed description of the Employee List page, its functionalities, and instructions on how to use it.
