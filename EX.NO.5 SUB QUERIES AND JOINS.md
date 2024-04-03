# EX.NO.5 SubQueries, Views and Joins 
### DATE 27/03/2024
## AIM
### To use SubQueries, Views and Joins in SQL 
## Create employee Table
```sql
CREATE TABLE EMP (EMPNO NUMBER(4) PRIMARY KEY,ENAME VARCHAR2(10),JOB VARCHAR2(9),MGR NUMBER(4),HIREDATE DATE,SAL NUMBER(7,2),COMM NUMBER(7,2),DEPTNO NUMBER(2));
```
## Insert the values
```sql
INSERT INTO EMP (EMPNO, ENAME, JOB, MGR, HIREDATE, SAL, COMM, DEPTNO)
VALUES (7369, 'SMITH', 'CLERK', 7902, '17-DEC-80', 800, NULL, 20);

INSERT INTO EMP (EMPNO, ENAME, JOB, MGR, HIREDATE, SAL, COMM, DEPTNO)
VALUES (7499, 'ALLEN', 'SALESMAN', 7698, '20-FEB-81', 1600, 300, 30);

INSERT INTO EMP (EMPNO, ENAME, JOB, MGR, HIREDATE, SAL, COMM, DEPTNO)
VALUES (7521, 'WARD', 'SALESMAN', 7698, '22-FEB-81', 1250, 500, 30);

INSERT INTO EMP (EMPNO, ENAME, JOB, MGR, HIREDATE, SAL, COMM, DEPTNO)
VALUES (7566, 'JONES', 'MANAGER', 7839, '02-APR-81', 2975, NULL, 20);

INSERT INTO EMP (EMPNO, ENAME, JOB, MGR, HIREDATE, SAL, COMM, DEPTNO)
VALUES (7654, 'MARTIN', 'SALESMAN', 7698, '28-SEP-81', 1250, 1400, 30);

INSERT INTO EMP (EMPNO, ENAME, JOB, MGR, HIREDATE, SAL, COMM, DEPTNO)
VALUES (7698, 'BLAKE', 'MANAGER', 7839, '01-MAY-81', 2850, NULL, 30);

INSERT INTO EMP (EMPNO, ENAME, JOB, MGR, HIREDATE, SAL, COMM, DEPTNO)
VALUES (7782, 'CLARK', 'MANAGER', 7839, '09-JUN-81', 2450, NULL, 10);

INSERT INTO EMP (EMPNO, ENAME, JOB, MGR, HIREDATE, SAL, COMM, DEPTNO)
VALUES (7788, 'SCOTT', 'ANALYST', 7566, '19-APR-87', 3000, NULL, 20);

INSERT INTO EMP (EMPNO, ENAME, JOB, MGR, HIREDATE, SAL, COMM, DEPTNO)
VALUES (7839, 'KING', 'PRESIDENT', NULL, '17-NOV-81', 5000, NULL, 10);

INSERT INTO EMP (EMPNO, ENAME, JOB, MGR, HIREDATE, SAL, COMM, DEPTNO)
VALUES (7844, 'TURNER', 'SALESMAN', 7698, '08-SEP-81', 1500, 0, 30);

INSERT INTO EMP (EMPNO, ENAME, JOB, MGR, HIREDATE, SAL, COMM, DEPTNO)
VALUES (7876, 'ADAMS', 'CLERK', 7788, '23-MAY-87', 1100, NULL, 20);

INSERT INTO EMP (EMPNO, ENAME, JOB, MGR, HIREDATE, SAL, COMM, DEPTNO)
VALUES (7900, 'JAMES', 'CLERK', 7698, '03-DEC-81', 950, NULL, 30);

INSERT INTO EMP (EMPNO, ENAME, JOB, MGR, HIREDATE, SAL, COMM, DEPTNO)
VALUES (7902, 'FORD', 'ANALYST', 7566, TO_DATE('03-DEC-81', 'DD-MON-RR'), 3000, 20, 20);

INSERT INTO EMP (EMPNO, ENAME, JOB, MGR, HIREDATE, SAL, COMM, DEPTNO)
VALUES (7934, 'MILLER', 'CLERK', 7782, TO_DATE('23-JAN-82', 'DD-MON-RR'), 1300, 10, 10);
```

## Create department table
```sql
CREATE TABLE DEPT (DEPTNO NUMBER(2) PRIMARY KEY,DNAME VARCHAR2(14),LOC VARCHAR2(13));
```
## Insert the values in the department table
```sql
INSERT INTO DEPT (DEPTNO, DNAME, LOC) VALUES (10, 'ACCOUNTING', 'NEW YORK');

INSERT INTO DEPT (DEPTNO, DNAME, LOC) VALUES (20, 'RESEARCH', 'DALLAS');

INSERT INTO DEPT (DEPTNO, DNAME, LOC) VALUES (30, 'SALES', 'CHICAGO');

INSERT INTO DEPT (DEPTNO, DNAME, LOC) VALUES (40, 'OPERATIONS', 'BOSTON');
```

### Q1) List the name of the employees whose salary is greater than that of employee with empno 7566.
```SQL
 select ename from emp where sal>(select sal from emp where empno=7566);
```

### QUERY:


### OUTPUT:
![281371918-d72df967-0777-4460-93ea-12ae21ad46a1](https://github.com/Prem-Kumar13122004/DBMS/assets/119291590/b9f10d76-075b-42fa-9e20-11ced82f746b)

### Q2) List the ename,job,sal of the employee who get minimum salary in the company.

### QUERY:
```SQL
 select ename,job,sal from emp where sal = (select min(sal) from emp);
```


### OUTPUT:
![281371970-f5bf807f-3daf-4c99-9ac0-9dd3455a3755](https://github.com/Prem-Kumar13122004/DBMS/assets/119291590/66b4d56f-d8bf-4aa0-a1e9-a1d7b5457ef7)

### Q3) List ename, job of the employees who work in deptno 10 and his/her job is any one of the job in the department ‘SALES’.

### QUERY:
```SQL
> SELECT ename, job
-> FROM emp
-> WHERE deptno = 10 AND job IN (SELECT job FROM emp WHERE job = 'SALES');
```


### OUTPUT:
![281372015-233a2663-0723-47df-ad50-b26b5ddef98d](https://github.com/Prem-Kumar13122004/DBMS/assets/119291590/7cb0f677-6f94-449b-a03f-b836eae4da3c)


### Q4) Create a view empv5 (for the table emp) that contains empno, ename, job of the employees who work in dept 10.

### QUERY:
```SQL
 CREATE VIEW emv5 AS SELECT empno, ename, job FROM emp WHERE deptno = 10;
```


### OUTPUT:
![281372244-306cc3af-bfbb-4ea7-a03b-7cce187e1291](https://github.com/Prem-Kumar13122004/DBMS/assets/119291590/21c74931-85fc-4c37-b3d4-988e70f37da3)

### Q5) Create a view with column aliases empv30 that contains empno, ename, sal of the employees who work in dept 30. Also display the contents of the view.

### QUERY:
```SQL
 CREATE VIEW emv30 AS SELECT empno AS `Employee Number`, ename AS `Employee Name`, sal AS `Salary` FROM emp WHERE deptno = 30;
```


### OUTPUT:
![281372534-4048bf4f-5d94-4f84-a20d-ad56e96db12c](https://github.com/Prem-Kumar13122004/DBMS/assets/119291590/5940df78-243e-450b-b99e-edca18f61e9d)


### Q6) Update the view empv5 by increasing 10% salary of the employees who work as ‘CLERK’. Also confirm the modifications in emp table

### QUERY:
```SQL
 UPDATE emv5 SET sal = sal * 1.1 WHERE job = 'CLERK';
 UPDATE emp
    -> SET sal = sal * 1.10
    -> WHERE job = 'CLERK';
```


### OUTPUT:
![281372560-342f579e-4bd4-4636-9ecf-0e58cb5ac52f](https://github.com/Prem-Kumar13122004/DBMS/assets/119291590/c27e0bce-9237-456f-9843-27187c2ea69b)
![281372624-17b79f6d-4e2f-4438-bc04-d943273238d5](https://github.com/Prem-Kumar13122004/DBMS/assets/119291590/0982f8e8-2037-413d-87f6-fc1b94915a2b)

## Create a Customer1 Table
```sql
CREATE TABLE Customer1 (customer_id INT,cust_name VARCHAR(20),city VARCHAR(20),grade INT,salesman_id INT);
```
## Inserting Values to the Table
```sql
INSERT INTO Customer1 (customer_id, cust_name, city, grade, salesman_id) VALUES(3002, 'Nick Rimando', 'New York', 100, 5001);
INSERT INTO Customer1 (customer_id, cust_name, city, grade, salesman_id) VALUES(3007, 'Brad Davis', 'New York', 200, 5001);
INSERT INTO Customer1 (customer_id, cust_name, city, grade, salesman_id) VALUES(3005, 'Graham Zusi', 'California', 200, 5002);
INSERT INTO Customer1 (customer_id, cust_name, city, grade, salesman_id) VALUES(3008, 'Julian Green', 'London', 300, 5002);
INSERT INTO Customer1 (customer_id, cust_name, city, grade, salesman_id) VALUES(3004, 'Fabian Johnson', 'Paris', 300, 5006);
INSERT INTO Customer1 (customer_id, cust_name, city, grade, salesman_id) VALUES(3009, 'Geoff Cameron', 'Berlin', 100, 5003);
INSERT INTO Customer1 (customer_id, cust_name, city, grade, salesman_id) VALUES(3003, 'Jozy Altidor', 'Moscow', 200, 5007);
INSERT INTO Customer1 (customer_id, cust_name, city, grade, salesman_id) VALUES(3001, 'Brad Guzan', 'London', NULL, 5005);
```
## Create a Salesperson1 table
```sql
CREATE TABLE Salesman1 (salesman_id INT,name VARCHAR(20),city VARCHAR(20),commission DECIMAL(4,2));
```
## Inserting Values to the Table
```sql
INSERT INTO Salesman1 (salesman_id, name, city, commission) VALUES(5001, 'James Hoog', 'New York', 0.15);
INSERT INTO Salesman1 (salesman_id, name, city, commission) VALUES(5002, 'Nail Knite', 'Paris', 0.13);
INSERT INTO Salesman1 (salesman_id, name, city, commission) VALUES(5005, 'Pit Alex', 'London', 0.11);
INSERT INTO Salesman1 (salesman_id, name, city, commission) VALUES(5006, 'Mc Lyon', 'Paris', 0.14);
INSERT INTO Salesman1 (salesman_id, name, city, commission) VALUES(5007, 'Paul Adam', 'Rome', 0.13);
INSERT INTO Salesman1 (salesman_id, name, city, commission) VALUES(5003, 'Lauson Hen', 'San Jose', 0.12);
```
### Q7) Write a SQL query to find the salesperson and customer who reside in the same city. Return Salesman, cust_name and city.

### QUERY:
```SQL
 SELECT salesman1.name AS "Salesman",
    ->        customer1.cust_name AS "Customer Name",
    ->        salesman1.city AS "City"
    -> FROM salesman1
    -> INNER JOIN customer1 ON salesman1.city = customer1.city;
```


### OUTPUT:
![281372675-2b195bd7-d33f-4497-9f4e-12d64a2eb3a6](https://github.com/Prem-Kumar13122004/DBMS/assets/119291590/b8aac7b8-1b20-442f-91e7-b51be4df626e)


### Q8) Write a SQL query to find salespeople who received commissions of more than 13 percent from the company. Return Customer Name, customer city, Salesman, commission.


### QUERY:
```SQL
 SELECT customer1.cust_name AS "Customer Name",
    ->        customer1.city AS "Customer City",
    ->        salesman1.name AS "Salesman",
    ->        salesman1.commission AS "Commission"
    -> FROM salesman1
    -> INNER JOIN customer1 ON salesman1.salesman_id = customer1.salesman_id
    -> WHERE salesman1.commission > 0.13;
```


### OUTPUT:
![281372716-5fbf0df5-c7f1-4601-92b0-dd3e3871a2d2](https://github.com/Prem-Kumar13122004/DBMS/assets/119291590/97285c8d-82a2-4703-acb6-c9c2e29bd1ce)


### Q9) Perform Natural join on both tables

### QUERY:
```SQL
 select * from Customer1 natural join salesman1;
```



### OUTPUT:
![281372987-eb42c972-4861-4835-a09f-32b6cda8eadb](https://github.com/Prem-Kumar13122004/DBMS/assets/119291590/f815a442-f60b-4204-b372-20bd4202c88a)

### Q10) Perform Left and right join on both tables

### QUERY:
```SQL
 SELECT *
    -> FROM salesman1
    -> LEFT JOIN customer1 ON salesman1.salesman_id = customer1.salesman_id;

 SELECT *
    -> FROM salesman1
    -> RIGHT JOIN customer1 ON salesman1.salesman_id = customer1.salesman_id;
```


### OUTPUT:
##LEFT JOIN
![281373031-f5c08fee-bda0-44c7-9360-c0f01230e579](https://github.com/Prem-Kumar13122004/DBMS/assets/119291590/67258c76-1d55-4578-a5af-9a8eb8366872)

##RIGHT JOIN
![281373063-0289b240-0edf-41e1-8a07-3b761deb72bd](https://github.com/Prem-Kumar13122004/DBMS/assets/119291590/5706f8e6-2ee9-4546-9df9-0c1238a84993)

## RESULT 
### Thus the basics of subqueries,views,joins are performed in SQL.
