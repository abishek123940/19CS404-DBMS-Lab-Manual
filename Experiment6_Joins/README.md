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

# **Question 1**
<img width="1365" height="985" alt="image" src="https://github.com/user-attachments/assets/0909d9bf-f613-4b35-9905-19e463f221e8" />


```sql
SELECT 
    o.ord_no,
    o.ord_date,
    o.purch_amt,
    c.cust_name AS "Customer Name",
    c.grade,
    s.name AS "Salesman",
    s.commission
FROM orders o
JOIN customer c 
    ON o.customer_id = c.customer_id
JOIN salesman s 
    ON o.salesman_id = s.salesman_id;
```

# **Output:**

<img width="1367" height="866" alt="image" src="https://github.com/user-attachments/assets/76017186-ecd6-45dc-b84c-51ec0ca5ebae" />

# **Question 2**
<img width="1288" height="457" alt="image" src="https://github.com/user-attachments/assets/7d89ab44-f268-49cd-9419-b644819b2c2f" />


```sql
select c.cust_name, c.city, o.ord_no, o.ord_date, o.purch_amt from customer c
left join orders o
on o.customer_id = c.customer_id where city = 'London';
```

# **Output:**

<img width="1336" height="452" alt="image" src="https://github.com/user-attachments/assets/25cc2aa8-7393-43c8-9505-bb63e4394f84" />

# **Question 3**
<img width="1326" height="611" alt="image" src="https://github.com/user-attachments/assets/fd5c671c-72e9-4f51-bd1b-46f74c8029b6" />


```sql
select p.first_name as patient_name, a.appointment_id, a.patient_id, a.doctor_id, a.appointment_date from patients p
inner join appointments a
on a.patient_id = p.patient_id;
```

# **Output:**

<img width="1333" height="529" alt="image" src="https://github.com/user-attachments/assets/da47c631-78e9-4de4-887e-d6fc32c4eb44" />

# **Question 4**
<img width="1336" height="797" alt="image" src="https://github.com/user-attachments/assets/df768ae6-10fd-49c3-8224-17205badfabd" />


```sql
select c.cust_name as "Customer Name", c.city, s.name as "Salesman", s.commission from customer c
join salesman s
on s.salesman_id = c.salesman_id;
```

# **Output:**

<img width="1337" height="802" alt="image" src="https://github.com/user-attachments/assets/ff674222-7ed5-48fc-865e-98376e71b8bd" />

# **Question 5**
<img width="1333" height="463" alt="image" src="https://github.com/user-attachments/assets/84c1f9ad-2692-4002-80ad-42ad673630c9" />


```sql
select s.name as "salesman_name", c.cust_name as "customer_name" from salesman s
left join customer c
on s.salesman_id = c.salesman_id;
```

# **Output:**

<img width="1337" height="809" alt="image" src="https://github.com/user-attachments/assets/3cf093b3-89e6-4c25-ae7c-64e95d1b0fbe" />

# **Question 6**
<img width="1330" height="771" alt="image" src="https://github.com/user-attachments/assets/ecf29e08-550c-4278-8533-d58387927d61" />


```sql
select c.cust_name as "Customer Name", c.city, s.name as "Salesman", s.commission from customer c
join salesman s
on s.salesman_id = c.salesman_id where commission > 0.12;
```

# **Output:**

<img width="1332" height="687" alt="image" src="https://github.com/user-attachments/assets/b0cf875d-0e99-4b91-9c99-d4578c91ff73" />

# **Question 7**
<img width="1334" height="575" alt="image" src="https://github.com/user-attachments/assets/6ec198a5-bbb5-4361-920f-8759de54e07c" />


```sql
select n.nurse_id, n.first_name, n.last_name, n.department_id from nurses n
inner join departments d
on d.department_id = n.department_id where department_name = "Pediatrics";
```

# **Output:**

<img width="1336" height="392" alt="image" src="https://github.com/user-attachments/assets/c70089d0-5b42-4a05-9b44-50d0b6fecd39" />

# **Question 8**
<img width="1330" height="678" alt="image" src="https://github.com/user-attachments/assets/41784087-2f4a-4ccd-b5c0-6c61a484360e" />


```sql
select p.*, d.specialization as "doctor_specialization" from patients p
inner join doctors d
on d.doctor_id = p.doctor_id;
```

# **Output:**

<img width="1338" height="532" alt="image" src="https://github.com/user-attachments/assets/51324db2-2d5c-43a9-b4c4-e67fe694d8b3" />

# **Question 9**
<img width="1335" height="788" alt="image" src="https://github.com/user-attachments/assets/3c812cd8-d2d9-420c-889c-3d37eb09453a" />


```sql
select c.cust_name, c.city, c.grade, s.name as "Salesman", s.city from customer c
join salesman s
on s.salesman_id = c.salesman_id order by customer_id asc;
```

# **Output:**

<img width="1331" height="806" alt="image" src="https://github.com/user-attachments/assets/e42f57b3-b20a-4b7f-82b8-eccf41844d39" />

# **Question 10**
<img width="1333" height="978" alt="image" src="https://github.com/user-attachments/assets/3bce67ca-69a5-4c6b-a3b2-2870c1b13556" />


```sql
SELECT 
    c.cust_name,
    c.city,
    o.ord_no,
    o.ord_date,
    o.purch_amt AS "Order Amount"
FROM customer c
LEFT JOIN orders o
    ON c.customer_id = o.customer_id
ORDER BY o.ord_date ASC;
```

# **Output:**

<img width="1345" height="978" alt="image" src="https://github.com/user-attachments/assets/b2f2e405-a52d-4619-b7f9-2e4cfa0d8cf8" />

**SEB Grade**
<img width="1367" height="76" alt="image" src="https://github.com/user-attachments/assets/bdc6860a-e450-4f8c-b2a7-edcf6dccaa05" />

## RESULT
Thus, the SQL queries to implement different types of joins have been executed successfully.
