# Name   : Harshini R
# REG NO : 212223220033

# Experiment 6: Joins

## AIM
To study and implement different types of joins.

## THEORY

SQL Joins are used to combine records from two or more tables based on a related column.

### 1. INNER JOIN
Returns records with matching values in both tables.

**Syntax:**
```sql
SELECT columns
FROM table1
INNER JOIN table2
ON table1.column = table2.column;
```

### 2. LEFT JOIN
Returns all records from the left table, and matched records from the right.

**Syntax:**

```sql
SELECT columns
FROM table1
LEFT JOIN table2
ON table1.column = table2.column;
```
### 3. RIGHT JOIN
Returns all records from the right table, and matched records from the left.

**Syntax:**

```sql
SELECT columns
FROM table1
RIGHT JOIN table2
ON table1.column = table2.column;
```
### 4. FULL OUTER JOIN
Returns all records when there is a match in either left or right table.

**Syntax:**

```sql
SELECT columns
FROM table1
FULL OUTER JOIN table2
ON table1.column = table2.column;
```

**Question 1**
--
![image](https://github.com/user-attachments/assets/ae6008b5-5737-4cdd-b4c7-fd1e318b555c)


```sql
   SELECT 
    c.cust_name,
    c.city,
    o.ord_no,
    o.ord_date,
    o.purch_amt AS "Order Amount",
    s.name,
    s.commission
FROM 
    customer c
LEFT JOIN 
    orders o ON c.customer_id = o.customer_id
LEFT JOIN 
    salesman s ON o.salesman_id = s.salesman_id
```

**Output:**

![image](https://github.com/user-attachments/assets/92c6b792-6527-4044-9b5e-7b669357c659)


**Question 2**
---
![image](https://github.com/user-attachments/assets/8fbd83c9-93c6-4421-9822-20d71c1d52ce)


```sql
SELECT
    p.date_of_birth,
    a.*
FROM
    patients p
INNER JOIN
    appointments a ON p.patient_id = a.patient_id
WHERE
    p.first_name = 'Alice';

```

**Output:**
![image](https://github.com/user-attachments/assets/405ada6b-a33d-4e85-b6ec-a4580eb8f0c4)


**Question 3**
---
![image](https://github.com/user-attachments/assets/256a6e75-ff70-46b8-9b64-519df95a2529)

```sql
SELECT
    c.cust_name AS "Customer Name",
    c.city,
    s.name AS "Salesman",
    s.commission
FROM
    customer c
JOIN
    salesman s ON c.salesman_id = s.salesman_id
WHERE
    s.commission > 0.12;

```

**Output:**

![image](https://github.com/user-attachments/assets/7e476525-e9a7-4691-bd1a-bdb862ed3052)


**Question 4**
---
![image](https://github.com/user-attachments/assets/ecec5612-8c46-4639-a430-7d539e915436)

```sql
SELECT
    p.*
FROM
    patients p
INNER JOIN
    appointments a ON p.patient_id = a.patient_id
WHERE
    a.appointment_date BETWEEN '2024-01-01' AND '2024-01-31';
```

**Output:**

![image](https://github.com/user-attachments/assets/10673800-ffd4-4cba-ac02-983a02877e00)


**Question 5**
---
![image](https://github.com/user-attachments/assets/7c422e77-2ca9-476f-ab41-72647468044e)


```sql
SELECT
    s.name AS Salesman,
    c.cust_name AS cust_name,
    s.city
FROM
    salesman s
JOIN
    customer c ON s.city = c.city;

```

**Output:**

![image](https://github.com/user-attachments/assets/8f5e5ccc-5f2b-42c5-b0e8-f9d1b04c8f13)

**Question 6**
---
![image](https://github.com/user-attachments/assets/972d0e98-b436-411f-a5f9-e7c01387e5eb)


```sql
SELECT 
    o.ord_no,
    o.purch_amt,
    o.ord_date,
    c.cust_name,
    c.city AS customer_city,
    c.grade,
    s.name AS salesman_name,
    s.city AS salesman_city,
    s.commission
FROM 
    orders o
INNER JOIN 
    customer c ON o.customer_id = c.customer_id
INNER JOIN 
    salesman s ON o.salesman_id = s.salesman_id;

```

**Output:**

![image](https://github.com/user-attachments/assets/0b601895-4bea-40b6-a29e-fbfa8c9d9181)


**Question 7**
---
![image](https://github.com/user-attachments/assets/bbabcd7f-bbef-434b-ad92-0891cd6c8a76)


```sql
SELECT 
    c.cust_name,
    o.ord_no,
    o.ord_date,
    o.purch_amt
FROM 
    customer c
LEFT JOIN 
    orders o ON c.customer_id = o.customer_id
WHERE 
    o.purch_amt > 1000;

```

**Output:**

![image](https://github.com/user-attachments/assets/4917fa33-8506-4abd-bc25-50055f9bb6e8)


**Question 8**
---
![image](https://github.com/user-attachments/assets/664af629-3765-4714-a1bb-eaa1de95d48b)


```sql
SELECT 
    o.ord_no,
    o.purch_amt,
    c.cust_name,
    c.city
FROM 
    orders o
JOIN 
    customer c ON o.customer_id = c.customer_id
WHERE 
    o.purch_amt BETWEEN 500 AND 2000;

```

**Output:**

![image](https://github.com/user-attachments/assets/61576767-0ac2-4065-aeda-3d0fcf72ce76)


**Question 9**
---
![image](https://github.com/user-attachments/assets/f4c1e152-cc9d-4420-a45d-7227134b0ad7)


```sql
SELECT 
    p.first_name AS patient_name,
    t.test_name
FROM 
    patients p
INNER JOIN 
    test_results t ON p.patient_id = t.patient_id;

```

**Output:**

![Output9](output.png)

**Question 10**
---
![image](https://github.com/user-attachments/assets/2c5cf845-ee3d-48f3-9b11-02cfaa1ef222)

```sql
SELECT 
    s.name,
    c.cust_name,
    c.city,
    c.grade,
    c.salesman_id
FROM 
    salesman s
LEFT JOIN 
    customer c ON s.salesman_id = c.salesman_id
WHERE 
    c.grade <= 100;

```

**Output:**

![image](https://github.com/user-attachments/assets/b9c7c8cc-1bc8-423a-aa9e-533e4df00256)



## RESULT
Thus, the SQL queries to implement different types of joins have been executed successfully.
