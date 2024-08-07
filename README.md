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

Certainly! Here’s a revised documentation for the Employee List page, incorporating the two components and additional details:

---

### Employee List Page Documentation

#### Overview
The Employee List page consists of two main components: **Employee List** and **Employee Profile**. This page allows users to view and manage employee information, including roles and reporting structures. 

#### Components

1. **Employee List**
   - Displays a list of all employees.
   - Features include:
     - **View Profile**: Opens detailed information about the selected employee.
     - **Edit Employee Position**: Allows users to update the employee's position.
     - **Batch Export**: Exports the employee data to CSV or JSON format based on user permissions.

2. **Employee Profile**
   - Provides detailed information about an individual employee.
   - Admin users have additional functionalities:
     - **Change Role**: Admins can modify the role of the employee within the system.
     - **Change Reports To**: Admins and editors can update the employee's reporting structure, specifying who the employee reports to.

#### Role-Based Access

- **Administrator**
  - Full access to all features:
    - View and edit employee profiles.
    - Change employee roles.
    - Update the reporting structure.
    - Export employee data.

- **Editor**
  - Can:
    - View and edit employee profiles.
    - Update the reporting structure.
    - Export employee data.

- **HR Manager**
  - Can:
    - View employee profiles.
    - Edit positions.
    - Export employee data.

- **Employee**
  - Can:
    - View their own profile only.

#### Usage Instructions

1. **Viewing Profiles**
   - Go to the Employee List page.
   - Click "View Profile" next to the desired employee to access their detailed profile.

2. **Editing Employee Position**
   - On the Employee List page, click "Edit" next to the employee's name.
   - Update the employee's position details and save changes.

3. **Changing Role**
   - In the Employee Profile, Admins can modify the employee’s role.
   - Click on the "Change Role" button and select the new role from the dropdown list.

4. **Changing Reports To**
   - In the Employee Profile, Admins and Editors can update the reporting structure.
   - Click on "Change Reports To" and select the appropriate manager or supervisor.

5. **Exporting Employee Data**
   - On the Employee List page, click the "Export" button.
   - Choose CSV or JSON format.
   - Confirm the export action to download the file.

#### Notes
- Ensure you have the necessary permissions to perform role changes or updates to reporting structures.
- For assistance or technical support, contact the system administrator.

---

This documentation provides a comprehensive overview of the Employee List page and its functionalities, detailing the access permissions and usage instructions for different roles.





Sure, here's a detailed documentation for the two pages: the "Module List Page" and the "Module Details Page."

## Module List Page

### Overview
The Module List Page displays all modules with their respective activity status and includes functionalities to add new modules, view module details, and manage module statuses. 

### Features

1. **Display Modules Information**: 
    - **Module Name**: Displays the name of the module.
    - **Activity Status**: Indicates whether the module is active or inactive.
    - **Additional Info**: Shows brief details about the module (e.g., description, creation date).

2. **Add New Module Button**: 
    - **Button**: A button labeled "Add New Module" to initiate the creation of a new module.
    - **Dropdown for Product Selection**: When clicked, it opens a form that includes a dropdown menu for selecting products. Only active products are shown in the dropdown.
    
3. **View Stats Button**: 
    - **Button**: A button labeled "View Stats" to display statistics related to the module (e.g., usage metrics, performance data).

4. **Perform Actions**:
    - **View Module**: 
        - **Button**: A button labeled "View" to see detailed information about the module.
        - **Details**: Opens a detailed view page displaying all departments, positions, and employees under the selected module.
    - **Deactivate Module**: 
        - **Button**: A button labeled "Deactivate" to soft delete the module, making it inactive without permanently removing it.
    - **Activate Module**: 
        - **Button**: A button labeled "Activate" to reactivate a previously deactivated module.
    - **Deactivate Batch**: 
        - **Button**: A button labeled "Deactivate Batch" to deactivate multiple modules at once.
    - **Activate Batch**: 
        - **Button**: A button labeled "Activate Batch" to reactivate multiple previously deactivated modules.

### User Interface

- **Table Layout**: The modules are displayed in a tabular format with columns for module name, activity status, actions, etc.
- **Action Buttons**: Action buttons are placed in a dedicated column, making it easy to perform actions on individual modules.

## Module Details Page

### Overview
The Module Details Page provides in-depth information about a specific module, including its departments, positions, and employees. It also allows for the management of the module's status.

### Features

1. **Module Information**: 
    - **Module Name**: Displays the name of the module.
    - **Description**: Provides a detailed description of the module.
    - **Activity Status**: Indicates the current activity status (active/inactive).

2. **Departments**: 
    - **List of Departments**: Displays all departments under the module.
    - **Department Info**: Shows brief details about each department (e.g., name, head of department).

3. **Positions**: 
    - **List of Positions**: Displays all positions under each department.
    - **Position Info**: Shows brief details about each position (e.g., title, reporting manager).

4. **Employees**: 
    - **List of Employees**: Displays all employees under each position.
    - **Employee Info**: Shows brief details about each employee (e.g., name, job title, contact info).

5. **Actions**:
    - **Activate/Deactivate Module**:
        - **Button**: A button to toggle the activity status of the module.
    - **Activate/Deactivate Batch**:
        - **Button**: A button to toggle the activity status of multiple modules at once.

### User Interface

- **Details Layout**: The page is structured to show hierarchical information, starting from the module, then departments, followed by positions, and finally employees.
- **Action Buttons**: Located prominently to ensure easy access for activating/deactivating the module or performing batch actions.

### Example Usage

1. **Adding a New Module**:
    - Click the "Add New Module" button.
    - Select an active product from the dropdown.
    - Fill in the required information and save the module.

2. **Viewing a Module**:
    - Click the "View" button next to the desired module.
    - Review detailed information about the module, its departments, positions, and employees.

3. **Managing Module Status**:
    - Click "Deactivate" to make a module inactive.
    - Click "Activate" to reactivate a module.
    - Use "Deactivate Batch" or "Activate Batch" to manage multiple modules at once.

This documentation covers the primary functionalities and layout of the Module List Page and the Module Details Page. Let me know if you need more detailed information or further assistance!

