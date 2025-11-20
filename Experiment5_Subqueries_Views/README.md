# Experiment 5: Subqueries and Views

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

# **Question 1**
<img width="1288" height="820" alt="image" src="https://github.com/user-attachments/assets/c440ce01-291b-4d8d-aa94-8d3b19ddd933" />


```sql
SELECT 
    o.ord_no, 
    o.purch_amt, 
    o.ord_date, 
    o.customer_id, 
    o.salesman_id
FROM 
    orders o
JOIN 
    salesman s 
ON 
    o.salesman_id = s.salesman_id
WHERE 
    s.city = 'New York';

```

# **Output:**

<img width="1286" height="569" alt="image" src="https://github.com/user-attachments/assets/d98e9eba-d9db-4118-b9ec-0329ddeeefe0" />

# **Question 2**
<img width="1290" height="851" alt="image" src="https://github.com/user-attachments/assets/3f448a74-7899-428a-bc95-6ff271ccc8bc" />


```sql
select o.ord_no, o.purch_amt, o.ord_date, o.salesman_id from orders o
join salesman s
on o.salesman_id = s.salesman_id
where s.commission = (select max(commission) from salesman);

```

# **Output:**

<img width="1285" height="561" alt="image" src="https://github.com/user-attachments/assets/13e412f5-36a4-4584-acfb-874be5ad00ee" />

# **Question 3**
<img width="1289" height="649" alt="image" src="https://github.com/user-attachments/assets/cea7f6e7-5487-4558-ab59-3a9192a76be2" />


```sql
SELECT ID, NAME, AGE, ADDRESS, SALARY FROM CUSTOMERS WHERE ADDRESS = 'Delhi' AND AGE < 30 ORDER BY ID ASC;
```

# **Output:**

<img width="1289" height="448" alt="image" src="https://github.com/user-attachments/assets/5ab4da7a-b8bd-44e9-b91e-3a793e07ef8a" />

# **Question 4**
<img width="1286" height="768" alt="image" src="https://github.com/user-attachments/assets/30fd543c-3bbc-40ec-a771-a6cbe222e677" />


```sql
SELECT * FROM CUSTOMERS WHERE SALARY > 1500;
```

# **Output:**
<img width="1285" height="691" alt="image" src="https://github.com/user-attachments/assets/e2734910-55dc-48fa-90a5-69543d05a415" />


# **Question 5**
<img width="1286" height="701" alt="image" src="https://github.com/user-attachments/assets/6c7a5a02-0032-45b3-9c1c-3ca06c3f85ba" />


```sql
SELECT * FROM CUSTOMERS WHERE SALARY < 2500;
```

# **Output:**
<img width="1289" height="545" alt="image" src="https://github.com/user-attachments/assets/4d3629d5-7eee-49ea-9ee7-9d8783a079bd" />


# **Question 6**
<img width="1285" height="648" alt="image" src="https://github.com/user-attachments/assets/03e36350-bfbc-48c9-a7b2-f376eba4cd03" />


```sql
select * from grades g where grade = (select max(grade) from grades where subject = g.subject);
```

# **Output:**

<img width="1288" height="539" alt="image" src="https://github.com/user-attachments/assets/ebd987c1-9f15-4387-a37e-3256c1e38449" />

# **Question 7**
<img width="1288" height="567" alt="image" src="https://github.com/user-attachments/assets/b840bc07-72e2-40a9-8e21-61b68ca9d4ec" />


```sql
select name, city from customer where city in (select city from customer where id in (3,7));
```

# **Output:**

<img width="1290" height="545" alt="image" src="https://github.com/user-attachments/assets/50e9d829-0292-4337-a7c6-7c68ba8b1d2d" />

# **Question 8**
<img width="1292" height="479" alt="image" src="https://github.com/user-attachments/assets/821173f3-2576-4cec-ba8b-6922d9af46b7" />


```sql
SELECT department_id, department_name FROM Departments
WHERE LENGTH(department_name) > (
    SELECT AVG(LENGTH(department_name))
    FROM Departments
);
```

# **Output:**

<img width="1294" height="489" alt="image" src="https://github.com/user-attachments/assets/2bbf2839-aeb6-424e-bae0-1c4afaf2c565" />

# **Question 9**
<img width="1284" height="640" alt="image" src="https://github.com/user-attachments/assets/e1478bc5-0c7b-46be-9f48-4476acded18b" />


```sql
SELECT *
FROM Employee
WHERE age < (
    SELECT AVG(age)
    FROM Employee
    WHERE income > 1000000
);
```

# **Output:**

<img width="1287" height="517" alt="image" src="https://github.com/user-attachments/assets/b2f3fb78-12d8-4cb1-9863-c3c039dee157" />

# **Question 10**
<img width="1285" height="674" alt="image" src="https://github.com/user-attachments/assets/261a4c6e-fd81-4f39-84ae-8efca4bd241e" />


```sql
select student_name, grade from GRADES g where grade = (select max(grade) from GRADES where subject = g.subject);
```

# **Output:**

<img width="1290" height="524" alt="image" src="https://github.com/user-attachments/assets/49a9213c-bafa-40fb-aeee-d866533f42b4" />

**SEB Grade**

<img width="1363" height="78" alt="image" src="https://github.com/user-attachments/assets/f3e58bf3-be90-44b6-9667-bf136b38cbc2" />

## RESULT
Thus, the SQL queries to implement subqueries and views have been executed successfully.
