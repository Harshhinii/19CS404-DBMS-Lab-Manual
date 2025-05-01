# Experiment 4: Aggregate Functions, Group By and Having Clause
# Name : Harshini R

## AIM
To study and implement aggregate functions, GROUP BY, and HAVING clause with suitable examples.

## THEORY

### Aggregate Functions
These perform calculations on a set of values and return a single value.

- **MIN()** – Smallest value  
- **MAX()** – Largest value  
- **COUNT()** – Number of rows  
- **SUM()** – Total of values  
- **AVG()** – Average of values

**Syntax:**
```sql
SELECT AGG_FUNC(column_name) FROM table_name WHERE condition;
```
### GROUP BY
Groups records with the same values in specified columns.
**Syntax:**
```sql
SELECT column_name, AGG_FUNC(column_name)
FROM table_name
GROUP BY column_name;
```
### HAVING
Filters the grouped records based on aggregate conditions.
**Syntax:**
```sql
SELECT column_name, AGG_FUNC(column_name)
FROM table_name
GROUP BY column_name
HAVING condition;
```

**Question 1**
--
![image](https://github.com/user-attachments/assets/49178341-f470-4857-a78e-5dee28ce4404)


```sql
occupation  AVG(workhour)
----------  -------------
Business    10.0
Engineer    12.0
```
```
SELECT
  occupation,
  AVG(workhour) AS "AVG(workhour)"
FROM
  employee1
GROUP BY
  occupation
HAVING
  AVG(workhour) BETWEEN 10 AND 12;
```

**Output:**

![image](https://github.com/user-attachments/assets/e5ce90fe-9951-4bb2-bb6d-22ffb1b54565)

**Question 2**
---
![image](https://github.com/user-attachments/assets/d3ef74f2-354b-46df-b2b8-27c917e9667f)


```sql
occupation  SUM(workhour)
----------  -------------
Business    30
Doctor      30
Engineer    24
Teacher     27
```
```
SELECT
  occupation,
  SUM(workhour) AS "SUM(workhour)"
FROM
  employee1
GROUP BY
  occupation
HAVING
  SUM(workhour) > 20;
```

**Output:**

![image](https://github.com/user-attachments/assets/26fbb399-acb1-45e4-9a00-27b9e81964da)

**Question 3**
---
![image](https://github.com/user-attachments/assets/4bce53ab-40a5-485f-991a-dc35e112fffe)


```sql
jdate       MAX(workhour)
----------  -------------
2004.0      15
2006.0      15
```
```
SELECT
  jdate,
  MAX(workhour) AS "MAX(workhour)"
FROM
  employee1
GROUP BY
  jdate
HAVING
  MAX(workhour) > 12;
```

**Output:**

![image](https://github.com/user-attachments/assets/f0859537-0a54-4b8e-a329-a12a379eeed5)


**Question 4**
---
![image](https://github.com/user-attachments/assets/22d0261c-5ace-4dc3-92e2-e96486c17689)


```sql
name        type
----------  ----------
id          INTEGER
name        TEXT   
city        TEXT
email       TEXT
phone       INTEGER
```
```
SELECT
  AVG(LENGTH(name)) AS avg_name_length
FROM
  customer
WHERE
  city = 'Chennai';
```

**Output:**

![image](https://github.com/user-attachments/assets/2dada2f9-e110-4281-aee6-9ea5e166527d)

**Question 5**
---
![image](https://github.com/user-attachments/assets/e172b781-cf1d-4caa-a8c8-c30f70eb3139)

```sql
SELECT
  COUNT(*) AS COUNT
FROM
  employee
WHERE
  age > 32;
```

**Output:**

![image](https://github.com/user-attachments/assets/3f8e934b-511d-4e88-b6a8-5c98d7a24d16)

**Question 6**
---![image](https://github.com/user-attachments/assets/514dc09e-b3c7-4799-95de-0b9f6d1bc0bf)


```sql
SELECT
  SUM(income) AS total_income
FROM
  employee
WHERE
  age >= 40;
```

**Output:**

![image](https://github.com/user-attachments/assets/e6a5eea2-c42d-4d41-80ff-12f28896568b)


**Question 7**
---
![image](https://github.com/user-attachments/assets/aa978068-7548-446c-9346-f0da3c67a480)


```sql
ord_no      purch_amt   ord_date    customer_id  salesman_id

----------  ----------  ----------  -----------  -----------

70001       150.5       2012-10-05  3005         5002

70009       270.65      2012-09-10  3001         5005

70002       65.26       2012-10-05  3002         5001
```
```
SELECT
  MAX(purch_amt) AS MAXIMUM
FROM
  orders;
```
**Output:**

![image](https://github.com/user-attachments/assets/4a8147ad-8fcd-4243-9bee-26578ad617de)


**Question 8**
---
![image](https://github.com/user-attachments/assets/e897e978-6547-48df-b3da-3eb098cb84fe)


```sql
PatientID   AvgMedications
----------  --------------
4           5
6           1
7           1
8           3

```
```
SELECT PatientID,COUNT(*) AS 
AvgMedications
FROM MedicalRecords
GROUP BY PatientID;
```
**Output:**

![image](https://github.com/user-attachments/assets/edc51390-35e5-4d8d-a252-fb2afbc10ba0)


**Question 9**
---
![image](https://github.com/user-attachments/assets/2602aaa2-9f1c-4fca-8c38-257c78052ba3)


```sql
Sample table: Patients Table

Address     TotalPatients
----------  -------------
Berlin      3
Chicago     4
Mexico      3
```
```
select Address,count(*)
as TotalPatients
from Patients
group by Address
```

**Output:**

![image](https://github.com/user-attachments/assets/978921b3-451b-4775-8e88-59542f3037cd)

**Question 10**
---
![image](https://github.com/user-attachments/assets/65e4b063-3c7c-42bc-beb2-3392b6fabef7)


```sql
Medication     AvgDosage
-------------  ----------
Ciprofloxacin  500.0
Doxorubicin    60.0
Ibuprofen      400.0
Levothyroxine  50.0
Lisinopril     10.0
MMR            0.5
Pending        0.0
Prenatal vita  1.0
Sertraline     50.0
Topiramate     25.0
```
```
SELECT
  Medication,
  AVG(Dosage) AS AvgDosage
FROM
  Prescriptions
GROUP BY
  Medication;
```

**Output:**

![image](https://github.com/user-attachments/assets/561cc520-8a8b-4413-9e0c-35795224c163)



## RESULT
Thus, the SQL queries to implement aggregate functions, GROUP BY, and HAVING clause have been executed successfully.
