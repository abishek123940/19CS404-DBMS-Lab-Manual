# Experiment 4: Aggregate Functions, Group By and Having Clause

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

# **Question 1**
<img width="1236" height="619" alt="image" src="https://github.com/user-attachments/assets/72c046d4-72ad-4dbb-8354-a336ecbc1de5" />


```sql
select PatientID, count(*) as TotalAppointments from Appointments group by PatientID;
```

# **Output:**

<img width="1239" height="716" alt="image" src="https://github.com/user-attachments/assets/9100927a-861a-42f8-95b7-5a8ffcda6b51" />

# **Question 2**
<img width="1233" height="673" alt="image" src="https://github.com/user-attachments/assets/dc2450e8-5fc7-4c1d-83ef-93f2038c6423" />


```sql
select Date(AppointmentDateTime) as AppointmentDate, count(*) as TotalAppointments from Appointments 
group by AppointmentDateTime;
```

# **Output:**

<img width="1238" height="743" alt="image" src="https://github.com/user-attachments/assets/eca3ef82-e813-40e5-a14c-a59f5c402de2" />

# **Question 3**
<img width="1239" height="455" alt="image" src="https://github.com/user-attachments/assets/8e840788-a21b-4e25-97b9-a221f3abdf4d" />


```sql
SELECT Diagnosis,COUNT(*) AS DiagnosisCount FROM MedicalRecords
GROUP BY Diagnosis
ORDER BY DiagnosisCount DESC
LIMIT 1;
```

# **Output:**

<img width="1238" height="400" alt="image" src="https://github.com/user-attachments/assets/753ddf02-44b0-4e86-abd4-b46c7011babc" />

# **Question 4**
<img width="1233" height="528" alt="image" src="https://github.com/user-attachments/assets/6149e3b5-222f-4939-b46a-93ed460a68fc" />


```sql
select max(purch_amt) as MAXIMUM from orders;
```

# **Output:**

<img width="1237" height="398" alt="image" src="https://github.com/user-attachments/assets/219ce4bc-2692-4e1e-93df-caec2760c1d9" />

# **Question 5**
<img width="1232" height="538" alt="image" src="https://github.com/user-attachments/assets/7ece726a-e11f-4198-ba1b-3e80f7afc95f" />


```sql
SELECT 
    name AS Employee_Name,
    age AS Age
FROM employee
ORDER BY age ASC
LIMIT 1;
```

# **Output:**

<img width="1239" height="395" alt="image" src="https://github.com/user-attachments/assets/b50572f2-35bf-4d50-a9ac-16e7b42f84aa" />

# **Question 6**
<img width="1237" height="526" alt="image" src="https://github.com/user-attachments/assets/33b18fbb-1ffb-4eb5-b577-323494760f7b" />


```sql
SELECT COUNT(*) AS employees_in_california FROM employee WHERE city = 'California';
```

# **Output:**

<img width="1237" height="403" alt="image" src="https://github.com/user-attachments/assets/94c87cb7-4088-4497-b230-3a01c40c87a9" />

# **Question 7**
<img width="1238" height="488" alt="image" src="https://github.com/user-attachments/assets/41a25c19-77e8-4018-81e3-17697798f857" />


```sql
SELECT 
    SUM(purch_amt) AS TOTAL
FROM orders;
```

# **Output:**

<img width="1235" height="396" alt="image" src="https://github.com/user-attachments/assets/94ff165f-9ede-40f2-b93c-d3ebbf8719e3" />

# **Question 8**
<img width="1233" height="572" alt="image" src="https://github.com/user-attachments/assets/9bca4df1-b77c-4608-8d1c-ec0d62149bff" />


```sql
SELECT 
    occupation,
    SUM(workhour)
FROM employee1
GROUP BY occupation
HAVING SUM(workhour) > 20;
```

# **Output:**

<img width="1238" height="549" alt="image" src="https://github.com/user-attachments/assets/03cdb1ea-f945-4675-bd57-0a072d3ee5a9" />

# **Question 9**
<img width="1232" height="510" alt="image" src="https://github.com/user-attachments/assets/abdc7680-fcd2-4899-9cd7-f825c162d7ed" />


```sql
SELECT 
    age,
    AVG(income)
FROM employee
GROUP BY age
HAVING AVG(income) BETWEEN 300000 AND 500000;
```

# **Output:**

<img width="1236" height="421" alt="image" src="https://github.com/user-attachments/assets/ec542927-9def-4b39-8962-24386d9cb2d3" />

# **Question 10**
<img width="1233" height="601" alt="image" src="https://github.com/user-attachments/assets/0dc4d8dc-8c75-42b5-bae3-46d1e100717a" />


```sql
SELECT 
    address,
    AVG(salary)
FROM customer1
GROUP BY address
HAVING AVG(salary) < 15000;
```

# **Output:**

<img width="1236" height="696" alt="image" src="https://github.com/user-attachments/assets/c11e9d1a-67ff-46d7-8658-2ec7e450b9b2" />

**SEB Grade**

<img width="1367" height="107" alt="image" src="https://github.com/user-attachments/assets/925ce49d-d328-4c7e-beed-a280382955ee" />

## RESULT
Thus, the SQL queries to implement aggregate functions, GROUP BY, and HAVING clause have been executed successfully.
