# Ex. No: 9 PL/SQL program using Triggers 
### DATE: 
### AIM: To create PL/SQL program to display new and old salary of customer when before/ after updation takes place. 

### Steps:
1. Create a trigger for each row when updation occurs.
2. Declare the variable in Declare section.
3. Start the begin section.
4. Calculate the salary changes.
5. Display the result 
6. End the begin section.

### Program:
```sql
CREATE TABLE employed(
  empid NUMBER,
  empname VARCHAR2(10),
  dept VARCHAR2(10),
  salary NUMBER
);

CREATE TABLE sal_log (
  log_id NUMBER GENERATED ALWAYS AS IDENTITY,
  empid NUMBER,
  empname VARCHAR2(10),
  old_salary NUMBER,
  new_salary NUMBER,
  update_date DATE
);
-- Insert the values in the employee table
insert into employed values(1,'Nagul','AIDS',1000000);
insert into employed values(2,'Santhosh','CSE',500000)
```
### Create employee table

![280044103-9ee3cc5f-8053-408a-ac14-1936fd4341ae](https://github.com/Prem-Kumar13122004/DBMS/assets/119291590/fd454145-12f1-489d-83dd-3b9f725ab9fa)


### Create salary_log table

![280044177-130a90ee-f128-4682-8362-76c2c94172c8](https://github.com/Prem-Kumar13122004/DBMS/assets/119291590/84b5f13f-e6de-40b9-8c67-e2b54392debd)



### PLSQL Trigger code
```sql
-- Create the trigger
CREATE OR REPLACE TRIGGER log_sal_update
BEFORE UPDATE ON employed
FOR EACH ROW
BEGIN
  IF :OLD.salary != :NEW.salary THEN
    INSERT INTO sal_log (empid, empname, old_salary, new_salary, update_date)
    VALUES (:OLD.empid, :OLD.empname, :OLD.salary, :NEW.salary, SYSDATE);
  END IF;
END;
/
-- Insert the values in the employee table
insert into employed values(1,'Nagul','AIDS',1000000);
insert into employed values(2,'Santhosh','SALES',500000);

-- Update the salary of an employee
UPDATE employed
SET salary = 60000
WHERE empid = 1;
-- Display the employee table
SELECT * FROM employed;

-- Display the salary_log table
SELECT * FROM sal_log;
```
### Output:
![280044318-3ba9322a-cf96-42f9-8879-90eed3cafbf4](https://github.com/Prem-Kumar13122004/DBMS/assets/119291590/f403cd9a-5775-4dd9-9cbb-6212548844ca)


![280044330-ee086f7e-2c85-4b00-9ced-1cd94ff7d49b](https://github.com/Prem-Kumar13122004/DBMS/assets/119291590/a19cdc61-db77-434b-93da-0c327c7862bf)


### Result:
Thust the program was performed sucessfully.
