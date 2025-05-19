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
![image](https://github.com/user-attachments/assets/9e87b687-cd8f-49de-a12a-cc6abef56261)


```

SELECT name
FROM customer
WHERE phone IN (
    SELECT phone
    FROM customer
    GROUP BY phone
    HAVING COUNT(*) = 1
);
```
**Output:**

![image](https://github.com/user-attachments/assets/4bf116ef-823c-43bf-bffd-fdd8985692ec)


**Question 2**

![image](https://github.com/user-attachments/assets/2f58bc63-6c1f-4c7e-b1b6-20085fc75c04)

```
SELECT *
FROM CUSTOMERS
WHERE SALARY > 4500;
```

**Output:**

![image](https://github.com/user-attachments/assets/487776a6-582e-42ad-81b8-70670d7fa7fc)

**Question 3**

![image](https://github.com/user-attachments/assets/0d5a4e87-6da0-4d58-aafe-3ea1e6965ed7)

```
SELECT *
FROM CUSTOMERS
WHERE ADDRESS = 'Delhi';
```

**Output:**

![image](https://github.com/user-attachments/assets/34464a28-48a4-47be-b6d1-42dee5f1b71d)

**Question 4**

![image](https://github.com/user-attachments/assets/740db1aa-dda1-48d4-8eb9-740aae92e58e)

```
SELECT *
FROM CUSTOMERS
WHERE SALARY < 2500;
```

**Output:**

![image](https://github.com/user-attachments/assets/2ad90826-bec9-4779-8d8e-6ce1a72c43a0)


**Question 5**

![image](https://github.com/user-attachments/assets/94c8a084-7001-425c-bf63-e0da308e48ce)

```
SELECT 
    ord_no, 
    purch_amt, 
    ord_date, 
    customer_id, 
    orders.salesman_id
FROM 
    orders
JOIN 
    salesman ON orders.salesman_id = salesman.salesman_id
WHERE 
    salesman.city = 'London';

```
**Output:**

![image](https://github.com/user-attachments/assets/f34ca043-3184-4490-806e-c490bb040674)

**Question 6**

![image](https://github.com/user-attachments/assets/b7cd803b-e8e6-4234-bc6f-541429f4295e)

```
SELECT *
FROM CUSTOMERS
WHERE SALARY > 1500;
```
**Output:**
![image](https://github.com/user-attachments/assets/e8ec7b02-b3c8-4e6f-aaaa-d8d4a14d00c6)


**Question 7**

![image](https://github.com/user-attachments/assets/bd2259b3-f059-42c3-9cee-0f6e08f85763)

```
SELECT *
FROM customer
WHERE customer_id = (
    SELECT salesman_id - 2001
    FROM salesman
    WHERE name = 'Mc Lyon'
);
```

**Output:**

![image](https://github.com/user-attachments/assets/e24eaf25-a4cd-4269-8da7-165890e024f2)

**Question 8**

![image](https://github.com/user-attachments/assets/644740d6-cd80-405d-9839-c10b932c8a67)

```
SELECT s.salesman_id, s.name
FROM salesman s
JOIN customer c ON s.salesman_id = c.salesman_id
GROUP BY s.salesman_id, s.name
HAVING COUNT(c.customer_id) > 1;
```
**Output:**

![image](https://github.com/user-attachments/assets/37efb837-f6ea-45e6-98d2-0cf54a5b7303)

**Question 9**

![image](https://github.com/user-attachments/assets/7e8b8005-0fe6-4783-9040-29c0cd45dd9d)

```
SELECT *
FROM customer
WHERE city <> (
    SELECT city
    FROM customer
    WHERE id = (SELECT MAX(id) FROM customer)
);
```
**Output:**

![image](https://github.com/user-attachments/assets/ce9b4556-c4ce-4de5-9a91-f9b820bda6bd)

**Question 10**
![image](https://github.com/user-attachments/assets/63fc42b5-52e6-4a67-be34-8787d0761384)

```
SELECT student_name,grade
FROM GRADES
WHERE grade = (
    SELECT MAX(grade)
    FROM GRADES AS g2
    WHERE g2.subject = GRADES.subject
);

```

**Output:**

![image](https://github.com/user-attachments/assets/a6789ed3-f76b-45a3-ab73-ec6d03d0ba48)

## RESULT
Thus, the SQL queries to implement subqueries and views have been executed successfully.
