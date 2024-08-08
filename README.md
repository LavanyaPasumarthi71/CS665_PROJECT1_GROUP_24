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
  - Limited to viewing profiles 
### Employee List Page Documentation

#### Overview
The Employee List page consists of two main components: **Employee List** and **Employee Profile**. This page allows users to view and manage employee information, including roles and reporting structures. 

#### 
This documentation provides a comprehensive overview of the Employee List page and its functionalities, detailing the access permissions and usage instructions for different roles.





Sure, here's a detailed documentation for the two pages: the "Module List Page" and the "Module Details Page."

## 
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
    - Click the "Add New Module" View" button next to the desired module.
    - Review detailed information about the module, its departments, positions, and employees.

3. **Managing Module Status**:
    - Click "Deactivate" to make a module inactive.
    - Click "Activate" to reactivate a module.
    - Use "Deactivate Batch" or "Activate Batch" to manage multiple modules at once.

This documentation covers the primary functionalities and layout of the Module List Page and the Module Details Page. Let me know if you need more detailed information or further assistance!

### List View Component Documentation

#### Overview
The List View component is a versatile UI element that displays detailed information in a tabular format. It also includes a search bar for filtering modules and provides functionality for managing employees and positions.

#### Features

1. **Display Information:**
   - The component displays all relevant details about employees and positions in a structured list or table format. This can include information such as employee names, positions, departments, and other relevant data.

2. **Search Bar:**
   - A search bar is included at the top of the list view, allowing users to filter the displayed information based on specific modules or keywords. The search function dynamically updates the list as the user types, making it easier to find specific entries.

3. **Action Buttons:**
   - The component includes several action buttons for managing employees and positions:
     - **Add Employee:** Opens a form to input details and add a new employee to the list.
     - **Add New Position:** Allows the user to define and add a new position to the system.
     - **Delete Position/Employee:** Enables the removal of an existing position or employee from the list. The delete action may prompt the user to confirm before finalizing the removal.

#### User Interactions

- **Adding an Employee:**
  - Users can click the "Add Employee" button to open a modal or form where they can input employee details such as name, position, and department. Once submitted, the new employee will appear in the list view.

- **Adding a New Position:**
  - By selecting the "Add New Position" button, users can define a new position by entering the position title, description, and any associated department. After saving, the new position will be available in the list.

- **Deleting a Position/Employee:**
  - The "Delete" action allows users to remove an employee or position. This action usually involves a confirmation step to prevent accidental deletions.

#### Code Structure

- **ListViewComponent:**
  - Responsible for rendering the list of employees and positions.
  - Contains logic for handling search input and filtering the displayed data.

- **SearchBarComponent:**
  - A child component within the ListView that handles user input for searching.
  - Triggers an update to the ListViewComponent to filter the displayed items based on the search criteria.

- **ActionButtonsComponent:**
  - Handles the add and delete actions.
  - Each button is tied to a specific function within the ListViewComponent to perform the corresponding operation.

#### Example Usage
```jsx
<ListViewComponent
  data={employeeData}
  onAddEmployee={handleAddEmployee}
  onAddPosition={handleAddPosition}
  onDelete={handleDelete}
/>
```

This documentation should provide a comprehensive overview of the List View component, detailing its features, user interactions, and code structure.
