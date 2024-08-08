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



Certainly! Here’s a detailed documentation for your Employee List 
3. **Managing Module Status**:
    - Click "Deactivate" to make a module inactive.
    - Click "Activate" to reactivate a module.
    - Use "Deactivate Batch" or "Activate Batch" to manage multiple modules at once.

This documentation covers the primary functionalities and layout of the Module List Page and the Module Details Page. Let me know if you need more detailed information or further 

### OrgChart Component Documentation

#### Overview
The OrgChart component visually represents the organizational hierarchy of products, modules, departments, positions, and employees. It offers a tree-like structure where users can expand or collapse nodes to explore different levels of the hierarchy. Additionally, it includes a search feature to locate specific employees within the hierarchy.

#### Features

1. **Tree Hierarchy Display:**
   - The OrgChart component represents the hierarchy in a tree structure with expandable nodes. The hierarchy is organized as follows:
     - **Products:** The top-level nodes representing different products.
     - **Modules:** Under each product, there are associated modules that can be expanded or collapsed.
     - **Departments:** Expanding a module reveals the departments related to that module.
     - **Positions:** Within each department, there are various positions.
     - **Employees:** Finally, each position node can be expanded to show the employees holding that position.

2. **Expand/Collapse Functionality:**
   - Users can click on any node to expand or collapse it, revealing or hiding the child nodes. This allows for an intuitive exploration of the organizational structure.

3. **Search Employee:**
   - The component includes a search bar at the top, enabling users to quickly find specific employees within the hierarchy. When a search is performed, the hierarchy auto-expands to display the node where the searched employee is located.

#### User Interactions

- **Expanding Nodes:**
  - Users can click on a product node to expand it and view the associated modules. Further clicks on the module, department, and position nodes will reveal additional hierarchical levels down to individual employees.

- **Collapsing Nodes:**
  - Nodes can be collapsed by clicking on them again, which hides their child nodes. This helps users manage the visibility of large amounts of data.

- **Searching for an Employee:**
  - Users can input an employee's name into the search bar. The component will search through the entire hierarchy, expand the relevant nodes, and highlight the employee's position within the hierarchy.

#### Code Structure

- **OrgChartComponent:**
  - This is the main component responsible for rendering the tree structure.
  - Manages the state of expanded/collapsed nodes and handles the search functionality.

- **TreeNodeComponent:**
  - Represents each node in the hierarchy (Product, Module, Department, Position, Employee).
  - Contains logic for toggling the expand/collapse state and for displaying child nodes.

- **SearchBarComponent:**
  - Handles user input for searching employees.
  - Triggers the expansion of the hierarchy to display the search results.

#### Example Usage
```jsx
<OrgChartComponent
  data={orgData}
  onSearch={handleSearch}
/>
```

#### Key Considerations

- **Performance:**
  - The component is optimized to handle large datasets by dynamically loading and rendering nodes only when they are expanded.
  
- **User Experience:**
  - The tree structure is designed to be intuitive, allowing users to navigate complex organizational structures with ease.

This documentation provides a detailed overview of the OrgChart component, outlining its features, user interactions, and code structure.
