# Experiment 3: DML Commands
# Name : Harshini R

## AIM
To study and implement DML (Data Manipulation Language) commands.

## THEORY

### 1. INSERT INTO
Used to add records into a relation.
These are three type of INSERT INTO queries which are as
A)Inserting a single record
**Syntax (Single Row):**
```sql
INSERT INTO table_name (field_1, field_2, ...) VALUES (value_1, value_2, ...);
```
**Syntax (Multiple Rows):**
```sql
INSERT INTO table_name (field_1, field_2, ...) VALUES
(value_1, value_2, ...),
(value_3, value_4, ...);
```
**Syntax (Insert from another table):**
```sql
INSERT INTO table_name SELECT * FROM other_table WHERE condition;
```
### 2. UPDATE
Used to modify records in a relation.
Syntax:
```sql
UPDATE table_name SET column1 = value1, column2 = value2 WHERE condition;
```
### 3. DELETE
Used to delete records from a relation.
**Syntax (All rows):**
```sql
DELETE FROM table_name;
```
**Syntax (Specific condition):**
```sql
DELETE FROM table_name WHERE condition;
```
### 4. SELECT
Used to retrieve records from a table.
**Syntax:**
```sql
SELECT column1, column2 FROM table_name WHERE condition;
```
**Question 1**
--
![image](https://github.com/user-attachments/assets/9fb17ddd-4bb8-4392-9ecb-b451a543f6eb)


```sql
delete from Customer
where GRADE >2 
and PAYMENT_AMT <(select avg(PAYMENT_AMT)from Customer)
or OUTSTANDING_AMT>8000;
```

**Output:**

![image](https://github.com/user-attachments/assets/be36d068-e3c1-475d-a900-79b14f8248d0)

**Question 2**
---
![image](https://github.com/user-attachments/assets/c5687193-1a9d-4062-b0d8-6e906992c478)


```sql
delete from Customer
where (GRADE=2 and CUST_NAME like 'M%')
and PAYMENT_AMT<3000;
```

**Output:**

![image](https://github.com/user-attachments/assets/ce4c15a1-ac1f-4559-9883-1638402e5a67)

**Question 3**
---
![image](https://github.com/user-attachments/assets/7e64055b-61dd-47db-9dce-3965b30e9f49)


```sql
delete from Surgeries
where surgery_id = 3;
```

**Output:**

![image](https://github.com/user-attachments/assets/608a5ace-cccd-4e5e-90ad-13381a170f17)


**Question 4**
---
![image](https://github.com/user-attachments/assets/1333e3c0-e36e-4d99-87c8-24308d1d2aca)


```sql
delete from Doctors
where doctor_id  = 1;
```

**Output:**

![image](https://github.com/user-attachments/assets/fc58d6ae-8aa4-4d5e-95b9-193c7cacb1ea)


**Question 5**
---
![image](https://github.com/user-attachments/assets/a341b77a-dc80-43ff-8dd6-ca147f4d59d5)

```sql
delete from Doctors
where specialization ='Cardiology';
```

**Output:**

![image](https://github.com/user-attachments/assets/c3f04ade-44ba-499f-b703-a8c3a371d0c3)

**Question 6**
---
![image](https://github.com/user-attachments/assets/6d1abb94-b9a7-4a61-8bd3-2af2e9436c1e)


```sql
update PRODUCTS
set reorder_lvl= reorder_lvl*0.7
where product_name like '%cream%' and quantity >reorder_lvl;
```

**Output:**

![image](https://github.com/user-attachments/assets/a07a3779-d2e4-4616-910c-e1676dd2e6a4)

**Question 7**
---
![image](https://github.com/user-attachments/assets/ed0d0237-90e5-4490-84f7-6d060d69cc62)

```sql
update products
set reorder_lvl=reorder_lvl*1.30
where category = 'Food' and quantity<50;
```

**Output:**

![image](https://github.com/user-attachments/assets/c1cb4a3b-67f0-4a8a-aebe-87cc89a52931)

**Question 8**
---
![image](https://github.com/user-attachments/assets/aa654afc-81e9-4aba-9a0f-fde48e9bd662)

```sql
update Employees
set EMAIL= 'not available' ,
COMMISSION_PCT =0.55
where department_id =110;
```

**Output:**

![image](https://github.com/user-attachments/assets/1136faf1-f61e-49fa-9438-43b8fcb8d884)

**Question 9**
---
![image](https://github.com/user-attachments/assets/257e5737-9cbd-4479-8b03-7f1d4933fe92)

```sql
update sales
set sell_price = sell_price +3
where product_id in(
select product_id
from PRODUCTS
where supplier_id=4);
```

**Output:**

![image](https://github.com/user-attachments/assets/a70d76e2-8e10-4867-a012-d3373eae2359)

**Question 10**
---
![image](https://github.com/user-attachments/assets/6a73d27b-5358-4e2b-8a88-b4b8a974356e)


```sql
update sales
set sell_price= sell_price*1.05
where product_id =15;
```

**Output:**

![image](https://github.com/user-attachments/assets/3c802866-a18a-4225-bec8-7fb7c1978db8)


## RESULT
Thus, the SQL queries to implement DML commands have been executed successfully.
