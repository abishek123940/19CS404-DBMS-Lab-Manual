# Experiment 3: DML Commands

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
# **Question 1**
<img width="1236" height="336" alt="image" src="https://github.com/user-attachments/assets/bf8e4a2f-81aa-42f1-9d41-bd11adc3f205" />


```sql
update products set product_name ="Premium Bread" where Product_id = 5;
```

# **Output:**

<img width="1233" height="489" alt="image" src="https://github.com/user-attachments/assets/49bfd35d-a4e9-4029-8fdc-f25d84ac2bf6" />

# **Question 2**
<img width="1237" height="331" alt="image" src="https://github.com/user-attachments/assets/20efcb87-c103-459c-bf1b-33031f6df05b" />


```sql
update products set sell_price = sell_price*1.10 where category = "Bakery";
```

# **Output:**

<img width="1233" height="612" alt="image" src="https://github.com/user-attachments/assets/3b9cf62d-b382-4c07-8b67-ab9c981a67c0" />

# **Question 3**
<img width="1237" height="687" alt="image" src="https://github.com/user-attachments/assets/680aa17c-6af2-4ddd-a287-3ec19a4995eb" />

```sql
update employees set email = "Unavailable";
```

# **Output:**

<img width="1236" height="539" alt="image" src="https://github.com/user-attachments/assets/447ec553-f986-425e-8db5-2a419a5bdcbf" />

# **Question 4**
<img width="1236" height="299" alt="image" src="https://github.com/user-attachments/assets/7da475da-5861-4ea4-a5ae-264cce89a15d" />


```sql
update sales set sell_price = sell_price*1.05 where product_id =15 and sale_date = "2023-01-31";
```

# **Output:**

<img width="1238" height="540" alt="image" src="https://github.com/user-attachments/assets/86ef006e-4114-4c44-9040-b1e579dd439d" />

# **Question 5**
<img width="1233" height="644" alt="image" src="https://github.com/user-attachments/assets/f83d92e7-dde8-4016-984d-f43d37600611" />


```sql
update employees set email = "not available",commission_pct = "0.55" where department_id = 110;
```

# **Output:**

<img width="1234" height="465" alt="image" src="https://github.com/user-attachments/assets/38a979c4-2277-4ec8-93cf-b8ee77b5f736" />

# **Question 6**
<img width="1235" height="159" alt="image" src="https://github.com/user-attachments/assets/bc58b474-7d15-4664-b93a-7b60a2e22f94" />


```sql
delete from doctors where specialization = "Cardiology";
```

# **Output:**

<img width="1239" height="474" alt="image" src="https://github.com/user-attachments/assets/1b7365cc-8d4b-46c9-bb60-0277fff9a776" />

# **Question 7**
<img width="1240" height="515" alt="image" src="https://github.com/user-attachments/assets/b926db82-c56d-4557-9413-53e13e8de35f" />


```sql
delete from surgeries where surgery_date = "2024-02-28";
```

# **Output:**

<img width="1239" height="472" alt="image" src="https://github.com/user-attachments/assets/57c1c6d9-c54e-4b1c-834b-e43d3fc7941f" />

# **Question 8**
<img width="1238" height="159" alt="image" src="https://github.com/user-attachments/assets/3e4ab02b-3f2e-44c6-bb4a-c81b010b2e01" />


```sql
delete from doctors where doctor_id = "1";
```

# **Output:**

<img width="1236" height="350" alt="image" src="https://github.com/user-attachments/assets/53962b6e-12ec-4298-af53-29df9618a3c9" />

# **Question 9**


```sql
delete from customer where CUST_NAME like "%Holmes%";
```

# **Output:**

<img width="1235" height="579" alt="image" src="https://github.com/user-attachments/assets/ee615739-bc80-4c49-a646-8ffb792c3bf7" />

# **Question 10**
<img width="1236" height="632" alt="image" src="https://github.com/user-attachments/assets/fd634778-da5f-42c2-ba9f-247964f73c0e" />


```sql
delete from customer where CUST_COUNTRY not in ("UK","USA","Canada") and GRADE>=3;
```

# **Output:**
<img width="1236" height="518" alt="image" src="https://github.com/user-attachments/assets/4a1ff90c-98dc-44a1-aa4d-3442abbb43f4" />

**SEB Grade**
<img width="1363" height="75" alt="image" src="https://github.com/user-attachments/assets/f91cd2ca-6998-497a-95e0-9435e4ba0885" />


## RESULT
Thus, the SQL queries to implement DML commands have been executed successfully.
