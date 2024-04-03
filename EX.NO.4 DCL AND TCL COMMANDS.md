# EX.NO 4 Data Control Language (DCL) Commands and Transaction Control Languages (TCL) in SQL
### DATE:
## AIM:
To create a manager database and execute DML queries using SQL.

# THEORY
## Data Control Language (DCL) commands
* Data control language (DCL) is used to access the stored data.
* It is mainly used for revoke and to grant the user the required access to a database.
## List of DCL commands: 
1. GRANT : It is used to insert data into a table.
2. REVOKE: It is used to update existing data within a table.
## Transaction control language(TCL) commands
1. COMMIT : COMMIT command in SQL is used to save all the transaction-related changes permanently to the disk
2. START TRANSACTION : to start the transaction
3. ROLLBACK : undo the transaction upto savepoint 
4. SAVEPOINT : create a savepoint to save the different parts of the same transaction using different names

### Q1) Create a table employee with employee id ,name and Address

### QUERY:
```
sql
create table employee(
emp_id numeric,
emp_name varchar(10),
addr varchar(40)
);
```

### OUTPUT:
![dbms exp 4 1](https://github.com/Prem-Kumar13122004/DBMS/assets/119291590/b8b497e9-6cac-4c4d-8be1-ed9fa9e142e4)

### Q2) Insert three rows into emploee table 


### QUERY:
```
sql
insert into employee values(1,'Luffy','EastBlue');
insert into employee values(2,'Shanks','GodValley');
insert into employee values(3,'Grap','MarinFord');
```
### OUTPUT:
![dbms exp4 2](https://github.com/Prem-Kumar13122004/DBMS/assets/119291590/3361f6a5-204f-43c4-aab9-1fe9e415c8d4)


### Q3) Start the transaction and create a save point s1.

### QUERY:
```
sql
savepoint A;
```

### OUTPUT:
![dbms exp4 3](https://github.com/Prem-Kumar13122004/DBMS/assets/119291590/fc71d67f-709a-47d6-afa2-1a7b71ca0c66)

### Q4) Perform insertion into employee table.

### QUERY:
```
sql
insert into employee(4,'Robin','EniesLobby');
```

### OUTPUT:
![dbms exp4 4](https://github.com/Prem-Kumar13122004/DBMS/assets/119291590/280410f0-dc27-4aae-8816-068aaf06c8d3)


### Q6)	Display the employee table and create a save point s2 .


### QUERY:
```
sql
select * from employee;
savepoint s2;
```

### OUTPUT:
![dbms exp4 6](https://github.com/Prem-Kumar13122004/DBMS/assets/119291590/423425a8-fa78-4748-a71c-026992740d0b)


### Q7)	Perform updation on any one of the row.


### QUERY:
```
sql
update employee set emp_name='Nico Robin' where emp_id=4;
```

### OUTPUT:
![dbms exp4 7](https://github.com/Prem-Kumar13122004/DBMS/assets/119291590/eed32fef-a07a-401d-9780-c508f7771a76)


### Q8) Display the employee table and rollback to  save point s2 


### QUERY:
```
sql
select * from employee;
rollback to s2;
```

### OUTPUT:
![dbms exp4 8](https://github.com/Prem-Kumar13122004/DBMS/assets/119291590/97e8e9d8-dc94-4a7b-9122-606279885159)


### Q9) Display the employee table and commit the changes; 


### QUERY:
```
sql
select * from employee;
commit;
```

### OUTPUT:
![dbms exp4 9](https://github.com/Prem-Kumar13122004/DBMS/assets/119291590/f12b0cc5-d5bc-4189-ae42-5849df71f106)


### Q10) Rollback to save point s1;


### QUERY:
```
sql
rollback to A;
```

### OUTPUT:
![dbms exp4 10](https://github.com/Prem-Kumar13122004/DBMS/assets/119291590/ee16a4be-86a4-4550-a462-a39ba338d922)


### Q11)	Create a new user and grant access to any one database with "insert and update"


### QUERY:
```
CREATE USER new_user;
GRANT INSERT, UPDATE ON database_name TO new_user;
```
### OUTPUT:
![dbms exp4 11](https://github.com/Prem-Kumar13122004/DBMS/assets/119291590/c361fd3d-fa12-49d2-a517-da997c82c6dc)


### Q12) Check the user access and display the result 


### QUERY:
SHOW GRANTS FOR new_user;

### OUTPUT:
![dbms exp4 12](https://github.com/Prem-Kumar13122004/DBMS/assets/119291590/440578a1-3999-4ba6-8b13-39a595077ccd)

### Q13) Revoke the privillages.

### QUERY:
```
SHOW GRANTS FOR new_user;
REVOKE INSERT, UPDATE ON database_name FROM new_user;
SHOW GRANTS FOR new_user;
```

### OUTPUT:
![dbms exp4 13](https://github.com/Prem-Kumar13122004/DBMS/assets/119291590/ff0cbdda-c5cd-4eed-b058-aabb11a1b00c)


## RESULT :
Thus the basic TCL and DCL commands are executed.
