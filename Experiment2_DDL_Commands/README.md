# Experiment 2: DDL Commands
# Name: Harshini R

## AIM
To study and implement DDL commands and different types of constraints.

## THEORY

### 1. CREATE
Used to create a new relation (table).

**Syntax:**
```sql
CREATE TABLE (
  field_1 data_type(size),
  field_2 data_type(size),
  ...
);
```
### 2. ALTER
Used to add, modify, drop, or rename fields in an existing relation.
(a) ADD
```sql
ALTER TABLE std ADD (Address CHAR(10));
```
(b) MODIFY
```sql
ALTER TABLE relation_name MODIFY (field_1 new_data_type(size));
```
(c) DROP
```sql
ALTER TABLE relation_name DROP COLUMN field_name;
```
(d) RENAME
```sql
ALTER TABLE relation_name RENAME COLUMN old_field_name TO new_field_name;
```
### 3. DROP TABLE
Used to permanently delete the structure and data of a table.
```sql
DROP TABLE relation_name;
```
### 4. RENAME
Used to rename an existing database object.
```sql
RENAME TABLE old_relation_name TO new_relation_name;
```
### CONSTRAINTS
Constraints are used to specify rules for the data in a table. If there is any violation between the constraint and the data action, the action is aborted by the constraint. It can be specified when the table is created (using CREATE TABLE) or after it is created (using ALTER TABLE).
### 1. NOT NULL
When a column is defined as NOT NULL, it becomes mandatory to enter a value in that column.
Syntax:
```sql
CREATE TABLE Table_Name (
  column_name data_type(size) NOT NULL
);
```
### 2. UNIQUE
Ensures that values in a column are unique.
Syntax:
```sql
CREATE TABLE Table_Name (
  column_name data_type(size) UNIQUE
);
```
### 3. CHECK
Specifies a condition that each row must satisfy.
Syntax:
```sql
CREATE TABLE Table_Name (
  column_name data_type(size) CHECK (logical_expression)
);
```
### 4. PRIMARY KEY
Used to uniquely identify each record in a table.
Properties:
Must contain unique values.
Cannot be null.
Should contain minimal fields.
Syntax:
```sql
CREATE TABLE Table_Name (
  column_name data_type(size) PRIMARY KEY
);
```
### 5. FOREIGN KEY
Used to reference the primary key of another table.
Syntax:
```sql
CREATE TABLE Table_Name (
  column_name data_type(size),
  FOREIGN KEY (column_name) REFERENCES other_table(column)
);
```
### 6. DEFAULT
Used to insert a default value into a column if no value is specified.

Syntax:
```sql
CREATE TABLE Table_Name (
  col_name1 data_type,
  col_name2 data_type,
  col_name3 data_type DEFAULT 'default_value'
);
```

**Question 1**
--
![image](https://github.com/user-attachments/assets/1d5eb1a3-377c-42ea-9cc5-265381c6f9be)


```sql
alter table  Student_details add  State TEXT;
```

**Output:**

![image](https://github.com/user-attachments/assets/56bcf4b2-9091-478b-a6aa-5129aca8ce7f)


**Question 2**
---
![image](https://github.com/user-attachments/assets/61058056-d04f-4c40-b2f7-a2906f6a0adc)

```sql
contact_id INTEGER primary key,
first_name TEXT not NULL,
last_name  TEXT  not NULL,
email TEXT,
phone  TEXT  not NULL check(length(phone)=10));
```

**Output:**

![image](https://github.com/user-attachments/assets/336e971d-6abb-4056-90f9-12c6084c6037)


**Question 3**
---
![image](https://github.com/user-attachments/assets/0252b04c-8fa7-4dfb-bffa-fccac8c1103e)

```sql
job_id int primary key,
job_title text,
min_salary integer default(8000),
max_salary int);
```

**Output:**

![image](https://github.com/user-attachments/assets/8af8f499-14e3-4e46-a50b-6aee55ee4b18)


**Question 4**
---
![image](https://github.com/user-attachments/assets/541e3d04-8b2b-4238-aa47-153148ea09a1)


```sql
InvoiceID INTEGER  primary key,
InvoiceDate DATE,
Amount  REAL check(Amount>0),
DueDate  DATE check(DueDate>InvoiceDate),
OrderID  INTEGER,
foreign key(OrderID) references Orders(OrderID));
```

**Output:**

![image](https://github.com/user-attachments/assets/2d137f94-0e1b-448e-82f0-398fa44297ba)


**Question 5**
---
![image](https://github.com/user-attachments/assets/b2e804fa-8709-44db-b237-da219849b92d)


```sql
alter table Employees add salary INTEGER check(salary>0);
```

**Output:**
![image](https://github.com/user-attachments/assets/f869202d-3af4-4b3f-9779-d66a31ca3b9a)


**Question 6**
---
![image](https://github.com/user-attachments/assets/d9201f7a-d68d-4c86-a7a0-65e4170ba68e)


```sql
select CustomerID, Name, Address, Email
from Old_customers;
```

**Output:**

![image](https://github.com/user-attachments/assets/b335dc2a-05bf-4a51-956e-fdc6e7b22616)


**Question 7**
---
![image](https://github.com/user-attachments/assets/474e2acf-c08e-4784-ae79-7f8f9221fff6)


```sql
```

**Output:**

![image](https://github.com/user-attachments/assets/a1d9333b-713b-4db0-9f33-b7ab9e5bc276)


**Question 8**
---
![image](https://github.com/user-attachments/assets/e546218a-65da-48f0-978d-0046fbbc7fa8)


```sql
TaskID  INTEGER,
TaskName TEXT,
DueDate DATE);
```

**Output:**

![image](https://github.com/user-attachments/assets/8580c97f-03cf-4901-a588-515a033f58f3)

**Question 9**
---
![image](https://github.com/user-attachments/assets/178810c4-a3a4-41c1-bad9-4436ed87394c)


```sql
OrderID INTEGER primary key,
OrderDate  DATE not NULL,
CustomerID INTEGER, 
foreign key(CustomerID) references Customers(CustomerID));
```

**Output:**

![image](https://github.com/user-attachments/assets/4996d3f1-5ff9-4c87-ba6c-7a14a47b4345)


**Question 10**
---
![image](https://github.com/user-attachments/assets/b21ac3ba-55c5-485f-8829-3582ffc04a57)


```sql
insert into Employee(EmployeeID,Name,Position,Department,Salary)values(7,'Noah Davis','Manager','HR',60000);
insert into Employee(EmployeeID,Name,Position,Department)values(8,'Ava Miller','Consultant','IT');
```

**Output:**
![image](https://github.com/user-attachments/assets/dc6f60d0-d0df-47f0-9f08-8fdedd0aa61c)

**grade:**
![image](https://github.com/user-attachments/assets/3747d324-61e6-452c-aa08-cf58c82ba10c)



## RESULT
Thus, the SQL queries to implement different types of constraints and DDL commands have been executed successfully.
