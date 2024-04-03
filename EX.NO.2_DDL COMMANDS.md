# EXP NO 2: DATA DEFINITION LANGUGE COMMANDS 
### DATE : 6.3.2024
## AIM:
To create a student database and execute DDL queries using SQL.


## THEORY
### DDL (Data Definition Language)

* DDL or Data Definition Language actually consists of the SQL commands that can be used to define the database schema.
* It simply deals with descriptions of the database schema and is used to create and modify the structure of database objects in the database.
* DDL is a set of SQL commands used to create, modify, and delete database structures but not data.
* These commands are normally not used by a general user, who should be accessing the database via an application.

 
### List of DDL commands: 
1. CREATE: This command is used to create the database or its objects (like table, index, function, views, store procedure, and triggers).
2. DROP: This command is used to delete objects from the database.
3. ALTER: This is used to alter the structure of the database.
4. TRUNCATE: This is used to remove all records from a table, including all spaces allocated for the records are removed.
5. RENAME: This is used to rename an object existing in the database.

## Query:
### 1) Create a database studentdb
create database studentdb
### SQL QUERY:

### OUTPUT:
![281321848-67c7b621-4f7a-4e8b-b315-f2e1eec02587](https://github.com/Prem-Kumar13122004/DBMS/assets/119291590/ec13f32c-47b7-4fe8-8e90-43d8a22040e7)

### 2) Create a table student  and insert any two rows with the following fieds RegisterNumber,Name,Age,Address,Phone number

### SQL QUERY: 
CREATE TABLE student (
    RegisterNumber INT PRIMARY KEY,
    Name VARCHAR(50),
    Age INT,
    Address VARCHAR(100),
    PhoneNumber VARCHAR(15)
);

INSERT INTO student (RegisterNumber, Name, Age, Address, PhoneNumber)
VALUES (101, 'Muzammil', 20, '123 Main St, Chennai', '9894499260'), (102, 'Prem', 20, '4 St, Salem', '9763457820');

### OUTPUT:
![dbms 2 (2)](https://github.com/Prem-Kumar13122004/DBMS/assets/119291590/31e858d0-6a1e-4c57-a99d-a66500682a5c)

### 3) Alter the above student table by adding another attribute department

### SQL QUERY: 
ALTER TABLE student ADD department VARCHAR(50);
### OUTPUT:
![dbms 2 (3)](https://github.com/Prem-Kumar13122004/DBMS/assets/119291590/9272d9ba-bbdc-4c2e-ae3a-a2722ed456f1)

### 4) Rename the student table to mystudent

### SQL QUERY: 
ALTER TABLE student RENAME TO mystudent;


### OUTPUT:
![dbms 2 (4)](https://github.com/Prem-Kumar13122004/DBMS/assets/119291590/cca5a03a-22ce-44b9-a688-cdd4ce49da31)

### 5) Delete the mystudent rows using truncate keyword

### SQL QUERY: 
TRUNCATE TABLE mystudent;

### OUTPUT:
![dbms 2 (5)](https://github.com/Prem-Kumar13122004/DBMS/assets/119291590/0dae80d1-bd3e-481a-ac20-ed8ef676fc59)

### 6) Drop the mystudent table
 
### SQL QUERY: 
DROP TABLE mystudent;

### OUTPUT:
![dbms 2 (6)](https://github.com/Prem-Kumar13122004/DBMS/assets/119291590/3c2287ec-ff00-41d1-8fc5-8e42262d04ee)









## Result:
         Thus the basic DDL commands in SQL are executed. 


