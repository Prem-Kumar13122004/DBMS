# EXP NO 1: ER DIAGRAM CREATION, RELATIONAL MODEL AND SCHEMA GENERATION  
### DATE : 6.3.2024
## AIM:
<div align="justify">
   To create a ER Diagram for Bank management system or College management system using ERD Plus tool and generate the relational model with schema. 
</div>

## Algorithm
1. Create a login with https://erdplus.com.
2. Create a new ER Diagram with name
3. Create a strong entity, relation and attributes.
4. Create a weak entity, relation and attributes.
5. Specify attributes unique, multivalued and composite attributes.

### ER Diagram 
![college erd](https://github.com/Prem-Kumar13122004/DBMS/assets/119291590/5b4c2ed4-233b-46d2-b8ab-dbc367af2018)


### Relational model

![college relational schema](https://github.com/Prem-Kumar13122004/DBMS/assets/119291590/c7409114-c659-477c-b80d-f701db50a28d)

### SQL DDL Schema 
```
CREATE TABLE COLLEGE
(
  CName INT NOT NULL,
  COffice INT NOT NULL,
  CPhone INT NOT NULL,
  PRIMARY KEY (CName)
);

CREATE TABLE INSTRUCTOR
(
  id INT NOT NULL,
  Rank INT NOT NULL,
  IOffice INT NOT NULL,
  IPhone INT NOT NULL,
  IName INT NOT NULL,
  PRIMARY KEY (id)
);

CREATE TABLE DEPT
(
  DName INT NOT NULL,
  DCode INT NOT NULL,
  DOffice INT NOT NULL,
  DPhone INT NOT NULL,
  PRIMARY KEY (DName),
  UNIQUE (DCode)
);

CREATE TABLE STUDENT
(
  Sid INT NOT NULL,
  FName INT NOT NULL,
  MName INT NOT NULL,
  DOB INT NOT NULL,
  Phno INT NOT NULL,
  PRIMARY KEY (Sid)
);

CREATE TABLE COURSE
(
  Credits INT NOT NULL,
  CDesc INT NOT NULL,
  Level INT NOT NULL,
  CCode INT NOT NULL,
  CoName INT NOT NULL,
  PRIMARY KEY (CCode),
  UNIQUE (CoName)
);

CREATE TABLE SECTION
(
  Secid INT NOT NULL,
  Year INT NOT NULL,
  Sem INT NOT NULL,
  DaysTime INT NOT NULL,
  PRIMARY KEY (Secid)
);
```
## RESULT 
<div align="justify">
Thus the ER diagram was drawn and relational diagram, SQL DDL staements are generated using ERD plus tool.
</div>
