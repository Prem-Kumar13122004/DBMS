# EXP NO 10: SYNONYMS AND ASSERTIONS IN SQL 
### DATE: 
## AIM:
To create a student database and create a synonym and assertions.

## THEORY
## SYNONYM
<div align="justify">
A SYNONYM provides another name for database object, referred to as original object, that may exist on a local or another server.
</div>
## ASSERTIONS
<div align="justify">
* An assertion is a piece of SQL which makes sure a condition is satisfied, else or it stops the action being taken on a database.
* An assertion is a constraint that might be dependent upon multiple rows of multiple tables.
</div>

## Query:
### 1) Create a table EMPLOYEE and perform insertion of two rows.

### SQL QUERY: 
```sql
CREATE TABLE EMPLOYEE (
    employee_id INT ,
    name VARCHAR(255),
    department VARCHAR(255),
    salary DECIMAL(10, 2)
);
```


### OUTPUT:
![277110918-71b5a740-3ed6-400c-a81e-55b48f5a29f8](https://github.com/Prem-Kumar13122004/DBMS/assets/119291590/c2cfcc98-38cd-4b2f-9be2-3ad6789a0a9e)

![277111028-f4d76026-48c5-4d61-a806-4befa6e93d93](https://github.com/Prem-Kumar13122004/DBMS/assets/119291590/72f0e69a-bedc-443b-836e-fe5deb4533a3)




### 2) Create a synonym S1 for EMPLOYEE  table.

### SQL QUERY: 
```sql
CREATE SYNONYM S1 FOR EMPLOYEE;
```

### OUTPUT:
![277111055-b455ceaa-8657-442e-b801-a7c7b7e87b67](https://github.com/Prem-Kumar13122004/DBMS/assets/119291590/731e48e5-016f-4a36-bb6a-fe42a9d90932)





### 3) Display the EMPLOYEE  table using synonym S1.
 
### SQL QUERY: 
```sql
SELECT * FROM S1;
```


### OUTPUT:

![277111121-6919a5b8-9f79-4180-a956-3df97ee88b03](https://github.com/Prem-Kumar13122004/DBMS/assets/119291590/8802d2d2-7df7-410a-ab14-1534b2f888ec)



### 4) Drop the synonym.

### SQL QUERY: 
```sql
DROP SYNONYM S1;
```


### OUTPUT:

![277111169-6368462e-e8b5-4451-8364-19a41290c302](https://github.com/Prem-Kumar13122004/DBMS/assets/119291590/68935bb2-c17b-4736-99c0-a9cc2dc5de79)



### 5) Create a supplier table and create a sequence S2 for supplier table id.

### SQL QUERY: 
```sql
CREATE TABLE supplier (
    id INT,
    name VARCHAR(255),
    address VARCHAR(255),
    contact_person VARCHAR(255)
);

CREATE SEQUENCE S2 START 1;

```


### OUTPUT:

![277111203-6941eec5-a29d-49f2-b642-9faa553c5710](https://github.com/Prem-Kumar13122004/DBMS/assets/119291590/a15674d8-7bf4-4056-97d3-dca3e9d56135)


![277111228-4fd3c19f-6eb2-433a-b260-cb701ca8daac](https://github.com/Prem-Kumar13122004/DBMS/assets/119291590/6f733ab1-b9a9-46e4-96f6-8063284e5d07)



### 6) insert the data into supplier table use sequence.

### SQL QUERY: 
```sql
INSERT INTO supplier (id, name, address, contact_person)
VALUES (NEXTVAL('S2'), 'ABC Suppliers', '123 Main Street', 'John Doe');

INSERT INTO supplier (id, name, address, contact_person)
VALUES (NEXTVAL('S2'), 'XYZ Distributors', '456 Elm Road', 'Jane Smith');
```


### OUTPUT:

![277111446-2f779d72-49da-4e24-8749-575d5625a31b](https://github.com/Prem-Kumar13122004/DBMS/assets/119291590/0f186e2a-328a-483d-b515-249f0a7d2191)



### 7) Drop the sequence

### SQL QUERY: 
```sql
DROP SEQUENCE S2;
```


### OUTPUT:

![277111327-bde530b6-caf5-48e6-96a6-e32d87846e74](https://github.com/Prem-Kumar13122004/DBMS/assets/119291590/8492f7bf-51dd-448f-988e-fa7bf9527e67)




## RESULT :
### Thus the sequence and synonym created and used in SQL.
