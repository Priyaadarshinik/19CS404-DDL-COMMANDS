# 19CS404-DDL-COMMANDS
# AIM: 
To study and implement DDL commands and different types of constraints. 
 
# THEORY: 
 
1. CREATE: 
This is used to create a new relation (table) 
 
Syntax: 
CREATE TABLE (field_1 data_type(size),field_2 data_type(size), .. . ); 
 
2. ALTER: 
This is used to add some extra fields into existing relation. 
 
Syntax: 
ALTER TABLE relation_name ADD (new field_1 data_type(size) ); 
 
(a) ALTER TABLE ...ADD...: 
ALTER TABLE std ADD (Address CHAR(10)); 
 
(b )ALTER TABLE...MODIFY...: 
ALTER TABLE relation_name MODIFY (field_1 newdata_type(Size) 
 
( c) ALTER TABLE..DROP.... 
ALTER TABLE relation_name DROP COLUMN (field_name); 
 
(d)ALTER TABLE..RENAME...: 
ALTER TABLE relation_name RENAME COLUMN (OLD field_name) to (NEW 
field_name); 
 
3.DROP TABLE: 
This is used to delete the structure of a relation. It permanently deletes the records in the 
table. 
 
Syntax: 
DROP TABLE relation_name; 
 
4.RENAME: 
It is used to modify the name of the existing database object. 
Syntax: 
RENAME TABLE old_relation_name TO new_relation_name; 
 
# CONSTRAINTS: 
 
Constraints are used to specify rules for the data in a table. If there is any violation between the 
constraint and the data action, the action is aborted by the constraint. It can be specified when the 
table is created (using CREATE TABLE statement) or after the table is created (using ALTER 
TABLE statement). 
 
# 1.NOT NULL:  
 
When a column is defined as NOTNULL, then that column becomes a mandatory column. It 
implies that a value must be entered into the column if the record is to be accepted for storage in 
the table. 
 
Syntax: 
CREATE TABLE Table_Name (column_name data_type (size) NOT NULL, ); 
 
 
# 2.UNIQUE:  
 
The purpose of a unique key is to ensure that information in the column(s) is unique 
i.e. a value entered in column(s) defined in the unique constraint must not be repeated across the 
column(s). A table may have many unique keys. 
 
Syntax: 
CREATE TABLE Table_Name(column_name data_type(size) UNIQUE, ….); 
 
# 3.CHECK:  
 
Specifies a condition that each row in the table must satisfy. To satisfy the constraint, each row in 
the table must make the condition either TRUE or unknown (due to a null). 
 
Syntax: 
CREATE TABLE Table_Name(column_name data_type(size) CHECK(logical 
expression), ….); 
 
# 4.PRIMARY KEY:  
 
A field which is used to identify a record uniquely. A column or combination of columns can be 
created as primary key, which can be used as a reference from other tables. A table contains 
primary key is known as Master Table. 
●It must uniquely identify each record in a table. 
●It must contain unique values. 
●It cannot be a null field. 
●It cannot be a multi port field. 
●It should contain a minimum number of fields necessary to be called unique. 
  
 
Syntax: 
CREATE TABLE Table_Name(column_name data_type(size) PRIMARY KEY, ….); 
 
# 5.FOREIGN KEY:  
 
It is a table level constraint. We cannot add this at column level. To reference any primary key 
column from other table this constraint can be used. The table in which the foreign key is defined 
is called a detail table. The table that defines the primary key and is referenced by the foreign key 
is called the master table. 
 
Syntax: 
CREATE TABLE Table_Name(column_name data_type(size)FOREIGN KEY(column_name) 
REFERENCES table_name); 
 
# 6.DEFAULT :  
 
The DEFAULT constraint is used to insert a default value into a column. The default value will 
be added to all new records, if no other value is specified. 
 
Syntax: 
CREATE TABLE Table_Name(col_name1,col_name2,col_name3 DEFAULT ‘’); 
 
# Question 1: 
 
Create a table named Products with the following constraints: 
• ProductID as INTEGER should be the primary key.
• ProductName as TEXT should be unique and not NULL. 
• Price as REAL should be greater than 0. 
• StockQuantity as INTEGER should be non-negative. 
 
# Answer: 
 
CREATE TABLE Products(ProductID INTEGER PRIMARY KEY, 
ProductName TEXT UNIQUE NOT NULL, Price REAL 
CHECK(Price>0),StockQuantity INTEGER CHECK(StockQuantity>=0)); 

# Output:
![image](https://github.com/user-attachments/assets/46c80db3-8cbd-45b3-9b87-17027acc045e)

   
# Question 2: 
 
Write an SQL query to add two new columns, department_id and manager_id, to 
the table employee with datatype of INTEGER. The manager_id column should 
have a default value of NULL. 
 
# Answer: 
 
ALTER TABLE employee 
ADD COLUMN department_id INTEGER; 
ALTER TABLE employee 
ADD COLUMN manager_id INTEGER DEFAULT NULL; 
 
# Output: 
 ![image](https://github.com/user-attachments/assets/24620da6-3ef6-4f6b-9e96-0cdf480c461e)
 
# Question 3: 
 
Insert all students from Archived_students table into the Student_details table. 
![image](https://github.com/user-attachments/assets/ed2e63cf-be3c-4b0b-88be-88aea27c64bc)


# Answer: 
 
INSERT INTO Student_details(RollNo,Name,Gender,Subject,MARKS) 
SELECT RollNo,Name,Gender,Subject,MARKS FROM Archived_students;  
 
 
# Output: 
![image](https://github.com/user-attachments/assets/1f6d742d-401e-4ecd-acaa-20f860128588)

# Question 4: 
 
Insert the following customers into the Customers table: 
![image](https://github.com/user-attachments/assets/f4832cd4-b0f3-4179-9316-473bd81dacbc)

# Answer: 
 
INSERT INTO Customers(CustomerID,Name,Address,City,ZipCode)  
VALUES (302,'Laura Croft','456 Elm St','Seattle','98101'); 
INSERT INTO Customers(CustomerID,Name,Address,City,ZipCode)  
VALUES (303,'Bruce Wayne','789 Oak St','Gotham','10001'); 
 
# Output: 
 ![image](https://github.com/user-attachments/assets/d443a4c6-5bba-42b0-9cc3-d8d5e5351050)
  
# Question 5: 
 
Write a SQL query to Add a new column Country as text in the Student_details 
table. 
Sample table: Student_details 

![image](https://github.com/user-attachments/assets/273ebf82-7f40-42cc-b5d1-42bfaaaca5cf)

# Answer: 
 
ALTER TABLE Student_details ADD COLUMN Country TEXT; 
 
 
# Output: 
![image](https://github.com/user-attachments/assets/2d971963-8b17-4216-ad05-e6d88b0c3a05)

# Question 6: 
 
Create a table named Events with the following columns: 
•EventID as INTEGER 
•EventName as TEXT 
•EventDate as DATE 
 
# Answer: 
 
CREATE TABLE Events(EventID INTEGER,EventName TEXT,EventDate 
DATE); 
 
# Output: 
![image](https://github.com/user-attachments/assets/f2fcac51-66b1-42e4-9267-b0aa6f31515f)


# Question 7: 
 
Create a table named ProjectAssignments with the following constraints: 
•AssignmentID as INTEGER should be the primary key. 
•EmployeeID as INTEGER should be a foreign key referencing 
Employees(EmployeeID). 
•ProjectID as INTEGER should be a foreign key referencing Projects(ProjectID). 
•AssignmentDate as DATE should be NOT NULL. 
 
# Answer: 
 
CREATE TABLE ProjectAssignments(AssignmentID INTEGER PRIMARY 
KEY,EmployeeID INTEGER,ProjectID INTEGER,AssignmentDate DATE NOT 
NULL, 
FOREIGN KEY(EmployeeID) REFERENCES 
Employees(EmployeeID),FOREIGN KEY(ProjectID) REFERENCES 
Projects(ProjectID)); 
 
# Output: 
![image](https://github.com/user-attachments/assets/635c743c-221f-42cd-ad42-0645f3396c71)
  
# Question 8: 
 
Write a SQL Query for inserting records with subquery 
 
Consider two tables, SourceTable and DestinationTable, where SourceTable 
contains information about individuals' ID, Name, and Age. Assume you want to 
insert records into DestinationTable from SourceTable where the Name is Kumar. 
Provide the SQL query for achieving this insertion using a subquery. 
 
 
# Answer: 
 
INSERT INTO DestinationTable SELECT * FROM SourceTable WHERE 
Name=='Kumar' 
 
 
# Output: 
 ![image](https://github.com/user-attachments/assets/4dc5513b-ec70-4b29-a0fa-373b41e22ace)

  
# Question 9: 
 
Write a SQL Query for inserting the below values as multiple row format in the 
table "Student" Note: In the Student Table attribute year set as default 3 
Sample Table:" Student" 
 
![image](https://github.com/user-attachments/assets/969d58c7-2111-4bc3-8b88-68761c1be659)

# Answer:          
 
INSERT INTO Student VALUES(3,'Jeni','Female','English',96,3); INSERT INTO 
Student 
VALUES(4,'Bob Johnson','Male','History',90,3); INSERT INTO Student 
VALUES(5,'Sharvesh','Male','Botany',97,3); INSERT INTO Student 
VALUES(6,'Mathew','Male','Science',85,3); 
 
 
# Output: 
![image](https://github.com/user-attachments/assets/1d0e74b8-a4b4-4a77-b552-ced29adac766)
 

# Question 10: 
 
Create a table named Attendance with the following constraints: 
• AttendanceID as INTEGER should be the primary key. 
• EmployeeID as INTEGER should be a foreign key referencing 
Employees(EmployeeID). 
• AttendanceDate as DATE. 
• Status as TEXT should be one of 'Present', 'Absent', 'Leave'. 
 
# Answer: 
 
CREATE TABLE Attendance(AttendanceID INTEGER PRIMARY 
KEY,EmployeeID INTEGER, AttendanceDate DATE,Status TEXT 
CHECK(Status IN ('Present','Absent','Leave')),FOREIGN 
KEY(EmployeeID)REFERENCES Employees(EmployeeID)); 
  
# Output: 
![image](https://github.com/user-attachments/assets/1f6c0089-a03c-420d-9c93-d26e24fd0f0b)

 
# Result: 
Thus , the SQL queries to implement different types of constraints and DDL 
commands have been executed
