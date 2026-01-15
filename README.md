
# MM2 Cinema Management System (Oracle Database)

##📌 Project Overview

*This project involves the design and implementation of a relational database system for MM2 Screen Management Sdn. Bhd. (MM Cineplexes). The database is designed to manage various aspects of cinema operations, including franchise management, staff administration, movie screenings, ticketing, inventory control, and customer data.

*The system is built using Oracle SQL and includes comprehensive scripts for creating the schema, populating data, and managing database objects.

##📂 Project Structure
The project consists of the following key files:

Create.sql: Contains DDL (Data Definition Language) commands to create all tables with appropriate data types, primary keys, foreign keys, and constraints (e.g., CHECK, UNIQUE).

InsertCode.sql: Contains DML (Data Manipulation Language) commands to populate the tables with sample data for testing and validation.

Drop.sql: A cleanup script to drop all tables and constraints in the correct order (handling dependencies) to reset the database.

Cinema EERD.jpg: The Entity Relationship Diagram (ERD) visualizing the database structure.

##🏗️ Database Schema Scope
The database supports the following key functional areas:

1. Person & Staff Management
Person: Central repository for all individuals (Staff, Customers).

Staff: General staff details.

Manager, Floor_Staff: Specialized roles with specific attributes (e.g., admin access, work area).

Shift, Attendance, Payslip, Leave: HR modules for tracking working hours, payments, and time off.

2. Cinema Operations
Franchise: Details of different franchise locations.

Cinema: Specific cinema branches linked to franchises.

Hall: Cinema halls with specific facilities (IMAX, 4DX, etc.).

Seat: Seating arrangements, availability, and types (VIP, Standard).

3. Movies & Ticketing
Movie: Information on movies, genres, ratings, and release dates.

Ticket: Booking details linking Customers, Movies, and Seats.

4. Customers
Customer: Base table for customer profiles.

Student_Customer, Kids_Customer, Senior_Citizen_Customer: Specialized profiles for targeted promotions and discounts.

5. Inventory & Products
Product, Food, Drink: Concession stand items.

Inventory, Storage, Stock_Supplier: Supply chain management for cinema stocks.

Asset, Asset_Log: Tracking cinema assets (projectors, speakers) and their maintenance.

6. Transactions & Feedback
C_Order: Customer orders for products/tickets.

Payment: Transaction records and refund statuses.

Review: Customer feedback and ratings.

##⚙️ Prerequisites
Oracle Database (11g, 12c, 19c, or later)

Oracle SQL Developer or any SQL command-line interface (SQL*Plus).

##🚀 Installation & Usage Instructions
To set up the database environment, run the SQL scripts in the following specific order to avoid constraint violations:

Step 1: Clean Up (Optional)
If you need to clear an existing version of the database, run the drop script.

SQL

@Drop.sql
Step 2: Create Schema
Run the create script to build the tables and relationships.

SQL

@Create.sql
Step 3: Populate Data
Run the insert script to load the sample data.

SQL

@InsertCode.sql
Step 4: Verification
You can verify the installation by running a simple query:

SQL

SELECT * FROM Cinema;
SELECT * FROM Person;
##📝 Key Features & Constraints
Data Integrity: Extensive use of Foreign Keys to ensure relationships (e.g., a Ticket must belong to a valid Movie and Hall).

Data Validation: CHECK constraints are used for fields like Staff_EmploymentStatus (Full-Time, Part-Time) and Ticket_Status (Booked, Cancelled).

Specialization: The design uses a supertype/subtype model for People (Person -> Staff/Customer) and Products (Product -> Food/Drink) to efficiently organize data.

##📜 License & Course Info
Course: TEB1103 (CS) Data and Information Management

Institution: Universiti Teknologi PETRONAS

Date: June 2025


