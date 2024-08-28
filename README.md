# MySQL-Comprehensive-Assessment #
____

# Library Management System #

## Overview ##

The Library Management System (LMS) is designed to manage and track the information about books, their availability, and transactions related to book issues and returns within a library. The system also manages data related to library branches, employees, and customers. This README provides an overview of the database structure, including tables, relationships, and some common SQL queries to retrieve essential information.

## Database Structure
___
The LMS database consists of the following tables:

### 1.	Branch
*	Branch_no (Primary Key): Unique identifier for each branch.
*	Manager_Id: Employee ID of the branch manager.
*	Branch_address: Physical address of the branch.
*	Contact_no: Contact number of the branch.

### 2.	Employee
*	Emp_Id (Primary Key): Unique identifier for each employee.
*	Emp_name: Name of the employee.
*	Position: Position of the employee within the branch.
*	Salary: Salary of the employee.
*	Branch_no (Foreign Key): References Branch_no in the Branch table.

##### 3.	Books
*	ISBN (Primary Key): Unique identifier for each book.
*	Book_title: Title of the book.
*	Category: Category/genre of the book.
*	Rental_Price: Rental price of the book.
*	Status: Availability status (Yes/No) of the book.
*	Author: Author of the book.
*	Publisher: Publisher of the book.

### 4.	Customer
*	Customer_Id (Primary Key): Unique identifier for each customer.
*	Customer_name: Name of the customer.
*	Customer_address: Address of the customer.
*	Reg_date: Registration date of the customer.

### 5.	IssueStatus
*	Issue_Id (Primary Key): Unique identifier for each issue transaction.
*	Issued_cust (Foreign Key): References Customer_Id in the Customer table.
*	Issued_book_name: Name of the issued book.
*	Issue_date: Date when the book was issued.
*	Isbn_book (Foreign Key): References ISBN in the Books table.

### 6.	ReturnStatus
*	Return_Id (Primary Key): Unique identifier for each return transaction.
*	Return_cust: Name of the customer returning the book.
*	Return_book_name: Name of the returned book.
*	Return_date: Date when the book was returned.
*	Isbn_book2 (Foreign Key): References ISBN in the Books table.
	
## Writing SQL Queries
___
1.	Retrieve available books:
*	Query the book title, category, and rental price of all available books.
2.	List employees by salary:
*	Query employee names and their salaries, sorted in descending order.
3.	Books issued to customers:
*	Query book titles and the corresponding customers who have issued them.
4.	Count books by category:
*	Query the total count of books in each category.
5.	Employees with high salaries:
*	Query employee names and positions for those earning above Rs. 50,000.
6.	Customers with no issues before 2022:
*	Query customer names who registered before 2022-01-01 and haven’t issued any books.
7.	Employee count per branch:
*	Query branch numbers and the total count of employees in each branch.
8.	Customers who issued books in June 2023:
*	Query customer names who issued books in June 2023.
9.	Books containing 'history':
*	Query book titles that contain the word "history".
10.	Branches with more than 5 employees:
*	Query branch numbers and employee counts where the count exceeds 5.
11.	Branch managers and their addresses:
*	Query names of employees who manage branches and their respective branch addresses.
12.	Customers who issued books with high rental prices:
*	Query names of customers who issued books with a rental price higher than Rs. 25.

## Conclusion
___
This Library Management System database design and the associated SQL queries provide a robust framework to manage and retrieve critical information efficiently. It tracks the availability, issue, and return of books while also maintaining the data related to employees, branches, and customers. This structure ensures smooth library operations and efficient data management.
