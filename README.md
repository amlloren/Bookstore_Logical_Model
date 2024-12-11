## Designing a Logical Model for a Small Bookstore
In this project, we explore the design and implementation of a logical database model tailored for a small bookstore. By addressing real-world challenges such as fragmented data storage and inefficient workforce scheduling, this project demonstrates how a well-structured database can enhance operational efficiency and decision-making. The proposed solution incorporates fundamental database principles and best practices, using tools like Draw.io and relational database management systems (DBMS) such as MySQL or PostgreSQL. Each business case within this project highlights a specific operational pain point and provides a data-driven solution to improve performance, organization, and customer satisfaction.

## Business Cases:
* [Establishing a Database](#business-case-1-establishing-a-scalable-database-for-bookstore-operations)
* [Optimizing Shift Management](#business-case-2-optimizing-workforce-scheduling-with-shift-management)

## Business Case #1: Establishing a Scalable Database for Bookstore Operations 

### Problem Statement:
The bookstore needs a structured and efficient way to store and manage data about its operations, including employees, customers, orders, sales, and inventory. Currently, the absence of an integrated system leads to fragmented data storage, making it difficult to analyze trends, track orders, and manage employee shifts effectively.

### Proposed Solution:
Design and implement a logical data model that integrates key aspects of bookstore operations. The model will include tables for employees, orders, sales, customers, books, and a date table to standardize and centralize data storage.

The relationships among these tables will ensure:
* Proper tracking of orders and sales.
* Management of employee records and work schedules.
* A single source of truth for inventory and customer information.

### Key Features of the Logical Model:
| feature | purpose |
|:-------:|---------|
| Employee Table | Tracks employee details like ID, name, and contact information, with a relationship to a shift table for scheduling. |
| Customer Table | Stores customer information, including ID, name, and optional address management (for potential future enhancements like delivery services). |
| Order Table | Records customer orders, linking to the book and customer tables for order details. |
| Sales Table | Tracks sales transactions with links to orders and dates for trend analysis. |
| Book Table | Maintains book inventory, including attributes like title, author, category, and stock levels. |
| Date Table | A centralized table for all date-related operations to simplify time-based reporting and analytics. |

### Implementation Tools:
* Design: Tools like Draw.io or LucidChart for visualization.
* Database Management System (DBMS): Any relational database like MySQL, PostgreSQL, or SQLite.

### Proposed Database Schema for a Small Bookstore.
![Schema 1](<images/SQL Assignment Q1.png>)

### Expected Outcomes:
* Centralized and well-organized data storage.
* Easier analysis of sales trends and inventory turnover.
* Improved operational decision-making by having access to structured, relational data.

## Business Case #2: Optimizing Workforce Scheduling with Shift Management

### Problem Statement:
The bookstore experiences fluctuating customer traffic throughout the day but lacks a structured way to schedule employees based on demand. Without dedicated shifts, the store struggles with overstaffing during slow hours and understaffing during peak periods, leading to increased labor costs and reduced customer satisfaction.

### Proposed Solution:
Introduce an Employee Shift Management System into the database schema by adding a SHIFT table. This table will organize employee schedules into morning and evening shifts, linked to the EMPLOYEE table and the DATE table. The system will enable the bookstore to track and manage employee availability, optimize labor distribution, and ensure sufficient staffing during peak hours.

### Key Features of the Enhanced Data Model:

1. Shift Table:
    * `shift_id`: Primary key to uniquely identify each shift.
    * `shift_name`: Descriptive names for shifts (e.g., "Morning", "Evening").
    * `start_time`: The start time of the shift.
    * `end_time`: The end time of the shift.

2. Employee-Shift Relationship:
    * Link employees to their assigned shifts through a foreign key in the `EMPLOYEE` table or a junction table (`EMPLOYEE_SHIFT`) if multiple employees can work the same shift.

3. Integration with Date Table:
    * Use the DATE table to manage shift schedules over time, allowing for historical data tracking and future planning.

### Implementation Example:
* A morning shift runs from 8:00 AM to 2:00 PM, while an evening shift runs from 2:00 PM to 8:00 PM.
* Each shift can have a defined number of employees based on expected customer traffic.

### Proposed Database Schema for a Small Bookstore.
![Question 2](<images/SQL Assignment Q2.png>)

### Expected Benefits:
* Better Resource Allocation: Ensure staffing levels match customer traffic patterns, reducing wait times and improving service.
* Cost Optimization: Minimize overstaffing during off-peak hours and avoid understaffing during busy periods.
Data-Driven Insights: Use shift data to analyze employee productivity and identify peak hours for further optimization.

### Implementation Tools:
* Use relational database design to implement the schema changes.
* Incorporate shift management into scheduling applications or dashboards.

### Outcome Example:
The bookstore notices that weekend evening shifts require more employees due to higher foot traffic. Using the shift data, it adjusts the schedule accordingly, leading to a 20% reduction in customer wait times and a 15% improvement in employee productivity.
