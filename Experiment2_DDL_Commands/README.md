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

# **Question 1**
<img width="1235" height="425" alt="image" src="https://github.com/user-attachments/assets/bfdb6710-ccb0-4fae-8a68-154814cd62f6" />

```sql
create table Tasks(
TaskID INTEGER,
TaskName TEXT,
DueDate DATE
)
```
# **Output:**

<img width="1234" height="467" alt="image" src="https://github.com/user-attachments/assets/cc733442-033f-4c7a-9756-c82b33a427e9" />


# **Question 2**

<img width="1233" height="496" alt="image" src="https://github.com/user-attachments/assets/12e0c7f7-6b7d-4b0a-b352-8206e7857a03" />

```sql
create table orders(
ord_id TEXT NOT NULL check(length(ord_id)=4),
item_id TEXT NOT NULL,
ord_date DATE,
ord_qty INTEGER,
cost INTEGER,
PRIMARY KEY (item_id,ord_date)
)
```

# **Output:**

<img width="1234" height="416" alt="image" src="https://github.com/user-attachments/assets/77560764-9843-4d20-86f6-3bd94cf297f2" />


# **Question 3**

<img width="1234" height="373" alt="image" src="https://github.com/user-attachments/assets/03032cf8-53b1-413e-b8bc-a7e6d6420d5b" />

```sql
alter table Student_details add column email TEXT NOT NULL DEFAULT 'Invalid'
```

# **Output:**

<img width="1235" height="325" alt="image" src="https://github.com/user-attachments/assets/e41bddb9-dd95-43d7-b5b3-ebe858f27f61" />

# **Question 4**
<img width="1235" height="419" alt="image" src="https://github.com/user-attachments/assets/b70c27ac-5a2f-4e3b-93eb-70cb41abad29" />


```sql
create table Products(
ProductID INTEGER PRIMARY KEY,
ProductName TEXT UNIQUE NOT NULL,
Price REAL check (Price>0),
StockQuantity INTEGER check (StockQuantity>=0)
)
```

# **Output:**

<img width="1238" height="378" alt="image" src="https://github.com/user-attachments/assets/ac725ef7-3995-43d2-84a7-ccc277e8df72" />


# **Question 5**

<img width="1235" height="372" alt="image" src="https://github.com/user-attachments/assets/17a34ced-3e31-4bbc-b092-d6d36b24db00" />

```sql
create table ProjectAssignments(
AssignmentID INTEGER PRIMARY KEY,
EmployeeID INTEGER,
ProjectID INTEGER,
AssignmentDate DATE NOT NULL,
FOREIGN KEY (EmployeeID) REFERENCES Employees(EmployeeID),
FOREIGN KEY (ProjectID) REFERENCES Projects(ProjectID)
)
```

# **Output:**

<img width="1241" height="369" alt="image" src="https://github.com/user-attachments/assets/deb32b76-87d2-4848-9d6f-fff49b42eb62" />

# **Question 6**
<img width="1240" height="352" alt="image" src="https://github.com/user-attachments/assets/1d861264-afa5-48cf-975d-fe628ce06deb" />


```sql
alter table customers add column email TEXT
```

# **Output:**

<img width="1237" height="379" alt="image" src="https://github.com/user-attachments/assets/6bcf4743-3dd9-414f-bdb7-c3a64877dac3" />

# **Question 7**
<img width="1230" height="412" alt="image" src="https://github.com/user-attachments/assets/f1a40d99-060a-481b-9520-2bcea59cde6a" />


```sql
insert into customers ("CustomerID","Name","Address","City","ZipCode") values ("302","Laura Croft","456 Elm St","Seattle","98101"),("303","Bruce Wayne","789 Oak St","Gotham","10001")
```

# **Output:**

<img width="1235" height="470" alt="image" src="https://github.com/user-attachments/assets/ec2d8c09-1960-43eb-9435-8315107000e2" />

# **Question 8**
<img width="1236" height="261" alt="image" src="https://github.com/user-attachments/assets/11d6f7b1-10fa-4b0b-b8a6-02cfab362e18" />


```sql
insert into Student_details ("RollNo","Name","Gender","Subject","MARKS") values (201,"David Lee","M","Physics",92)
```

# **Output:**

<img width="1236" height="324" alt="image" src="https://github.com/user-attachments/assets/2735ec96-43d3-4a30-b5bb-f3b325905533" />

# **Question 9**
<img width="1234" height="476" alt="image" src="https://github.com/user-attachments/assets/cc0a23cd-9a95-4df5-a526-2c37e61baa8c" />


```sql
CREATE TABLE item (
item_id    TEXT PRIMARY KEY,
item_desc  TEXT NOT NULL,
rate       INTEGER NOT NULL,
icom_id    TEXT check(length(icom_id)=4),
FOREIGN KEY (icom_id) REFERENCES company(com_id) ON UPDATE CASCADE ON DELETE CASCADE
);
```

# **Output:**

<img width="1237" height="443" alt="image" src="https://github.com/user-attachments/assets/1e81ca20-f093-4df5-b1f0-a3d02637ad12" />

# **Question 10**
<img width="1232" height="374" alt="image" src="https://github.com/user-attachments/assets/70b5840e-b5da-4b36-813b-5bee390da405" />


```sql
insert into Employee("EmployeeID","Name","Department","Salary")
select EmployeeID, Name, Department, Salary from Former_employees
```

# **Output:**

<img width="1237" height="359" alt="image" src="https://github.com/user-attachments/assets/3560d43b-228b-417f-9626-008a5ee1d5e8" />

**SEB Grade** 

<img width="1363" height="76" alt="image" src="https://github.com/user-attachments/assets/6be724fc-5e68-437a-a070-2cef9e5594e8" />

## RESULT
Thus, the SQL queries to implement different types of constraints and DDL commands have been executed successfully.

