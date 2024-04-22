# Bookstore Database Project

This is a sample database project for a bookstore. It includes tables for books, authors, stores, employees, customers, transactions, writes (which establishes the relationship between books and authors), and inventory.

Tables
BOOK
BookID (INT): Unique identifier for each book.
BookName (VARCHAR(255)): Name of the book.
Genre (CHAR(50)): Genre of the book.
DateOfPublication (DATE): Publication date of the book.
ISBN (INT): ISBN number of the book.
NumberOfBooks (INT): Number of copies available.
Primary Key: BookID
AUTHOR
AuthorID (INT): Unique identifier for each author.
AuthorName (CHAR(100)): Name of the author.
Primary Key: AuthorID
STORE
StoreID (INT): Unique identifier for each store.
City (CHAR(50)): City where the store is located.
State (CHAR(2)): State where the store is located.
Primary Key: StoreID
EMPLOYEE
EmployeeID (INT): Unique identifier for each employee.
EmployeeName (CHAR(100)): Name of the employee.
NumOfHrsWrkd (FLOAT): Number of hours worked by the employee.
StoreID (INT): Identifier for the store where the employee works.
Primary Key: EmployeeID
Foreign Key: StoreID (References StoreID in STORE table)
CUSTOMER
CustomerID (INT): Unique identifier for each customer.
CustomerName (CHAR(100)): Name of the customer.
Primary Key: CustomerID
TRANSACTION
TransactionID (INT): Unique identifier for each transaction.
Amount (FLOAT): Amount of the transaction.
EmployeeID (INT): Identifier for the employee handling the transaction.
CustomerID (INT): Identifier for the customer making the transaction.
BookID (INT): Identifier for the book involved in the transaction.
Primary Key: TransactionID
Foreign Keys: EmployeeID (References EmployeeID in EMPLOYEE table), CustomerID (References CustomerID in CUSTOMER table), BookID (References BookID in BOOK table)
WRITES
BookID (INT): Identifier for the book.
AuthorID (INT): Identifier for the author.
Primary Key: (BookID, AuthorID)
Foreign Keys: BookID (References BookID in BOOK table), AuthorID (References AuthorID in AUTHOR table)
INVENTORY
StoreID (INT): Identifier for the store.
BookID (INT): Identifier for the book.
NumberOfBooks (INT): Number of copies of the book in the store's inventory.
Primary Key: (StoreID, BookID)
Foreign Keys: StoreID (References StoreID in STORE table), BookID (References BookID in BOOK table)
Purpose
This database is designed to manage a bookstore's inventory, transactions, employees, customers, authors, and stores. It allows tracking of books, their genres, publication dates, authors, store locations, employees, customers, and transactions.

Usage
This database can be used by bookstore owners or managers to:

Track inventory levels of books in each store.
Record transactions including the book sold, the customer, and the employee involved.
Manage employee information such as names, hours worked, and store assignments.
Keep track of customer information for loyalty programs or marketing purposes.
Associate books with their authors.
Getting Started
To use this database, you can:

Create the tables in a PostgreSQL database using the provided SQL script.
Populate the tables with sample data.
Run queries to retrieve information about books, authors, stores, employees, customers, transactions, and inventory.
Contributing
Contributions to improve the database structure or documentation are welcome. Feel free to fork this repository, make your changes, and submit a pull request.
