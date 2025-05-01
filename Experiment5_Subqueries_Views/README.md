# Experiment 5: Subqueries and Views
# Name: Harshini R
# Reg.No :212223220033

## AIM
To study and implement subqueries and views.

## THEORY

### Subqueries
A subquery is a query inside another SQL query and is embedded in:
- WHERE clause
- HAVING clause
- FROM clause

**Types:**
- **Single-row subquery**:
  Sub queries can also return more than one value. Such results should be made use along with the operators in and any.
- **Multiple-row subquery**:
  Here more than one subquery is used. These multiple sub queries are combined by means of ‘and’ & ‘or’ keywords.
- **Correlated subquery**:
  A subquery is evaluated once for the entire parent statement whereas a correlated Sub query is evaluated once per row processed by the parent statement.

**Example:**
```sql
SELECT * FROM employees
WHERE salary > (SELECT AVG(salary) FROM employees);
```
### Views
A view is a virtual table based on the result of an SQL SELECT query.
**Create View:**
```sql
CREATE VIEW view_name AS
SELECT column1, column2 FROM table_name WHERE condition;
```
**Drop View:**
```sql
DROP VIEW view_name;
```

**Question 1**
--
![image](https://github.com/user-attachments/assets/0fe75c01-c92b-44f5-b849-8900d1fc716e)

```sql
SELECT department_id,department_name from Departments WHERE LENGTH (department_name)> ( SELECT AVG(LENGTH(department_name)) FROM Departments )
```
**Output:**

![image](https://github.com/user-attachments/assets/ab21e3a1-a156-4672-a89e-247233375321)

**Question 2**
---
Write a SQL query to retrieve all columns from the CUSTOMERS table for customers whose salary is greater than $1500.

Sample table: CUSTOMERS

ID NAME AGE ADDRESS SALARY

1 Ramesh 32 Ahmedabad 2000 2 Khilan 25 Delhi 1500 3 Kaushik 23 Kota 2000 4 Chaitali 25 Mumbai 6500 5 Hardik 27 Bhopal 8500 6 Komal 22 Hyderabad 4500

7 Muffy 24 Indore 10000

SELECT * FROM CUSTOMERS WHERE SALARY > 1500;

**Output:**

![image](https://github.com/user-attachments/assets/af6bdf67-56df-4a4d-ad32-48513cce4d64)

**Question 3**
---
Write a SQL query to Find employees who have an age less than the average age of employees with incomes over 2.5 Lakh

SELECT id,name,age,city,income FROM Employee WHERE age < ( SELECT AVG(age) FROM Employee WHERE income > 250000 );

**Output:**

![image](https://github.com/user-attachments/assets/6b85db83-becb-4ce4-99ff-4287a248a463)

**Question 4**
---
Write a SQL query to retrieve all columns from the CUSTOMERS table for customers whose AGE is LESS than $30

Sample table: CUSTOMERS

ID NAME AGE ADDRESS SALARY

1 Ramesh 32 Ahmedabad 2000 2 Khilan 25 Delhi 1500 3 Kaushik 23 Kota 2000 4 Chaitali 25 Mumbai 6500 5 Hardik 27 Bhopal 8500 6 Komal 22 Hyderabad 4500

7 Muffy 24 Indore 10000

SELECT * FROM CUSTOMERS WHERE AGE < 30;

**Output:**

![image](https://github.com/user-attachments/assets/e1adde0d-aa54-4f64-a3b4-eb4684aad03e)

**Question 5**
---
Write a SQL query to retrieve all columns from the CUSTOMERS table for customers whose Address as Delhi

Sample table: CUSTOMERS

ID NAME AGE ADDRESS SALARY

1 Ramesh 32 Ahmedabad 2000 2 Khilan 25 Delhi 1500 3 Kaushik 23 Kota 2000 4 Chaitali 25 Mumbai 6500 5 Hardik 27 Bhopal 8500 6 Komal 22 Hyderabad 4500

7 Muffy 24 Indore 10000

SELECT * FROM CUSTOMERS WHERE ADDRESS = 'Delhi';
**Output:**

![image](https://github.com/user-attachments/assets/ff1e1225-e138-4cab-a319-85199638e584)

**Question 6**

From the following tables write a SQL query to find salespeople who had more than one customer. Return salesman_id and name.

salesman table

name type

salesman_id numeric(5) name varchar(30) city varchar(15) commission decimal(5,2)

customer table

name type

customer_id int cust_name text city text grade int salesman_id int

SELECT s.salesman_id, s.name FROM salesman s JOIN customer c ON s.salesman_id = c.salesman_id GROUP BY s.salesman_id, s.name HAVING COUNT(c.customer_id) > 1;
**Output:**

![image](https://github.com/user-attachments/assets/cce3cd31-10c2-48e8-8910-089a042d252f)

**Question 7**
Write a query to display all the customers whose ID is the difference between the salesperson ID of Mc Lyon and 2001.

salesman table

name type

salesman_id numeric(5) name varchar(30) city varchar(15) commission decimal(5,2)

customer table

name type

customer_id int cust_name text city text grade int salesman_id int

SELECT * FROM customer WHERE customer_id = ( SELECT s.salesman_id - 2001 FROM salesman s WHERE s.name = 'Mc Lyon' );

**Output:**

![image](https://github.com/user-attachments/assets/3af95ee4-a545-4605-aecf-137cbc388ba2)


**Question 8**
Write a SQL query to retrieve all columns from the CUSTOMERS table for customers whose salary is greater than $4500.

Sample table: CUSTOMERS

ID NAME AGE ADDRESS SALARY

1 Ramesh 32 Ahmedabad 2000 2 Khilan 25 Delhi 1500 3 Kaushik 23 Kota 2000 4 Chaitali 25 Mumbai 6500 5 Hardik 27 Bhopal 8500 6 Komal 22 Hyderabad 4500

7 Muffy 24 Indore 10000

SELECT * FROM CUSTOMERS WHERE SALARY > 4500;

**Output:**

![image](https://github.com/user-attachments/assets/b6609d38-6013-4003-8088-242e94922110)

**Question 9**
Write a SQL query to Retrieve the names of customers who have a phone number that is not shared with any other customer.

SAMPLE TABLE: customer

name type

id INTEGER name TEXT city TEXT email TEXT phone INTEGER

SELECT name FROM customer WHERE phone NOT IN ( SELECT phone FROM customer GROUP BY phone HAVING COUNT(*) > 1 );

**Output:**

![Output9](output.png)

**Question 10**
Write a SQL query that retrieve all the columns from the table "Grades", where the grade is equal to the maximum grade achieved in each subject.

SELECT * FROM Grades g WHERE grade = ( SELECT MAX(grade) FROM Grades WHERE subject = g.subject GROUP BY subject );

**Output:**

![image](https://github.com/user-attachments/assets/9f21a23c-bc36-4de7-9198-9ce4ad675e92)



## RESULT
Thus, the SQL queries to implement subqueries and views have been executed successfully.
