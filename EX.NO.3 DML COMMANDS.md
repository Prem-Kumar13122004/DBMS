# EX 2 Data Manipulation Language (DML) Commands and built in functions in SQL
## AIM:
To create a manager database and execute DML queries using SQL.

# THEORY
## DML(Data Manipulation Language)
*  The SQL commands that deal with the manipulation of data present in the database belong to DML or Data Manipulation Language and this includes most of the SQL statements.
*  It is the component of the SQL statement that controls access to data and to the database. Basically, DCL statements are grouped with DML statements.

## List of DML commands: 
1. INSERT: It is used to insert data into a table.
2. UPDATE: It is used to update existing data within a table.
3. DELETE: It is used to delete records from a database table.
4. SELECT: The SELECT command shows the records of the specified table.

## Create the table as given below:
```sql
create table manager(enumber number(6),ename char(15),salary number(5),commission number(4),annualsalary number(7),Hiredate date,designation char(10),deptno number(2),reporting char(10));
```
## insert the following values into the table
```sql
insert into manager values(7369,'Dharsan',2500,500,30000,'30-June-81','clerk',10,'John');
insert into manager values(7839,'Subu',3000,400,36000,'1-Jul-82','manager',null,'James');
insert into manager values(7934,'Aadhi',3500,300,42000,'1-May-82','manager',30,NULL);
insert into manager values(7788,'Vikash',4000,0,48000,'12-Aug-82','clerk',50,'Bond');
```

### Q1) Update all the records of manager table by increasing 10% of their salary as bonus.

### QUERY:
```
UPDATE manager
SET salary = salary + (salary * 0.1),
    annualsalary = annualsalary + (annualsalary * 0.1)
```

### OUTPUT:
![dbms 3exp 1](https://github.com/DrUmaRaniV/DBMS/assets/119291590/cfda95ee-7aaf-44b0-9696-b75485c7d7ea)


### Q2) Delete the records from manager table where the salary less than 2750.


### QUERY:
```
DELETE FROM manager
WHERE salary < 2750;
```

### OUTPUT:
![dbms exp3 2](https://github.com/DrUmaRaniV/DBMS/assets/119291590/3db7c979-e37d-4693-9dcd-8809d3890bca)

### Q3) Display each name of the employee as “Name” and annual salary as “Annual Salary” (Note: Salary in emp table is the monthly salary)


### QUERY:
```
select ename as "Name", salary * 12 as "Annual Salary"
from manager;
```


### OUTPUT:
![dbms  exp3 3](https://github.com/DrUmaRaniV/DBMS/assets/119291590/aa4845e4-fb22-4a13-b84e-fdf5cf50d27b)

### Q5)	List the names of Clerks from emp table.


### QUERY:


### OUTPUT:


### Q6)	List the names of employee who are not Managers.


### QUERY:


### OUTPUT:


### Q7)	List the names of employees not eligible for commission.


### QUERY:


### OUTPUT:


### Q8)	List employees whose name either start or end with ‘s’.


### QUERY:


### OUTPUT:


### Q9) Sort emp table in ascending order by hire-date and list ename, job, deptno and hire-date.


### QUERY:


### OUTPUT:


### Q10) List the Details of Employees who have joined before 30 Sept 81.


### QUERY:


### OUTPUT:


### Q11)	List ename, deptno and sal after sorting emp table in ascending order by deptno and then descending order by sal.


### QUERY:


### OUTPUT:


### Q12) List the names of employees not belonging to dept no 30,40 & 10


### QUERY:


### OUTPUT:

### Q13) Find number of rows in the table EMP

### QUERY:


### OUTPUT:


### Q14) Find maximum, minimum and average salary in EMP table.

### QUERY:


### OUTPUT:


### Q15) List the jobs and number of employees in each job. The result should be in the descending order of the number of employees.

### QUERY:


### OUTPUT:


## RESULT :
Thus the basic DML commands are executed.
