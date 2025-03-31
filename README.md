# PBLJ_7_E18497

Easy Level: Fetch Data from MySQL Database
Problem Statement: Create a Java program to connect to a MySQL database and fetch data from a table named Employee with the columns EmpID, Name, and Salary. The program should:

Use DriverManager and Connection objects.

Retrieve and display all records from the Employee table.

Solution Theory:

In Java, to connect to a MySQL database and fetch data, the following basic steps are performed:

Database Connection: Use JDBC (Java Database Connectivity) API to establish a connection with the database. The DriverManager class is used to load the database driver, and Connection object is used to interact with the database.

Statement: After establishing the connection, use a Statement or PreparedStatement object to execute SQL queries.

ResultSet: The ResultSet object is used to retrieve the data returned by a SELECT query.

Close Connections: Always close the ResultSet, Statement, and Connection objects to free up resources.

Steps for JDBC Connection:

Import necessary packages (java.sql.*).

Load the MySQL driver using Class.forName("com.mysql.cj.jdbc.Driver").

Establish a connection using DriverManager.getConnection().

Execute a SQL SELECT query using Statement.executeQuery().

Process the result with ResultSet and display the records.

Sample Input and Output:

Input:
 
SELECT * FROM Employee;
Output:

markdown
Copy
EmpID | Name         | Salary
--------------------------------
1     | John Doe     | 50000
2     | Jane Smith   | 60000
3     | Mike Johnson | 55000
Medium Level: CRUD Operations on Product Table
Problem Statement: Build a program to perform CRUD operations (Create, Read, Update, Delete) on a database table Product with the columns ProductID, ProductName, Price, and Quantity. The program should include:

Menu-driven options for each operation.

Transaction handling to ensure data integrity.

Solution Theory:

To perform CRUD operations, JDBC provides several methods such as executeUpdate() for creating, updating, or deleting records and executeQuery() for reading data.

Steps for CRUD Operations:

Create Operation: Insert new records into the table using INSERT INTO.

Read Operation: Retrieve records from the table using SELECT.

Update Operation: Modify existing records using UPDATE.

Delete Operation: Remove records using DELETE.

Transaction Handling: To ensure data integrity, JDBC supports transaction management. By default, each SQL statement is treated as a single transaction. Using Connection.setAutoCommit(false), you can disable auto-commit mode and manage transactions manually, committing them with commit() or rolling them back with rollback() in case of errors.

Menu-Driven Interface: The program can prompt the user for an operation (1 for Create, 2 for Read, etc.) and allow the user to input the necessary data for the operation. If the user selects an option, the corresponding CRUD operation is performed.

Sample Input and Output:

Input:
 
 
Menu:
1. Create Product
2. Read Product
3. Update Product
4. Delete Product
Enter your choice: 1
Enter Product Name: Laptop
Enter Price: 1000
Enter Quantity: 50
Output:

 
Product successfully added to the database.
Hard Level: MVC Architecture for Student Data Management
Problem Statement: Develop a Java application using JDBC and MVC architecture to manage student data. The application should:

Use a Student class as the model with fields like StudentID, Name, Department, and Marks.

Include a database table to store student data.

Allow the user to perform CRUD operations through a simple menu-driven view.

Implement database operations in a separate controller class.

Solution Theory:

In this scenario, we are using the MVC (Model-View-Controller) architecture to organize the code. The MVC pattern separates the concerns of the application into three main components:

Model: This represents the data structure. The Student class will act as the model that contains the student data attributes (e.g., StudentID, Name, Department, Marks).

View: The user interface (UI) that interacts with the user and displays data. The view prompts the user for input and displays the results of CRUD operations.

Controller: The controller handles the logic for performing CRUD operations and interacts with the database. It communicates with both the model and the view.

Steps for Implementing the Application:

Model (Student Class): Create a Student class that encapsulates the student's data.

Controller (Database Operations): Write a controller class to handle the database operations. This class will interact with the Student model to fetch, insert, update, and delete records.

View (Menu & User Input): Create a user interface that presents the CRUD options to the user and accepts inputs for each operation.

Database Setup: Create a table named Student with fields StudentID, Name, Department, and Marks.

Database Table (Student):

 
CREATE TABLE Student (
    StudentID INT PRIMARY KEY,
    Name VARCHAR(100),
    Department VARCHAR(50),
    Marks INT
);
Sample Flow:

Create Operation: Allow the user to input student details and insert them into the database.

Read Operation: Display all student records or a specific student by their StudentID.

Update Operation: Modify the details of an existing student.

Delete Operation: Delete a student record by StudentID.

Sample Input and Output:

Input (Menu-driven interface):

 
Menu:
1. Add Student
2. View Student
3. Update Student
4. Delete Student
Enter your choice: 1
Enter Student Name: John Doe
Enter Department: Computer Science
Enter Marks: 85
Output:
 
Student added successfully!
