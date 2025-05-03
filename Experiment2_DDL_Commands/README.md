# Experiment 2: DDL Commands

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

**Question 1**
--
![Screenshot 2025-05-03 142746](https://github.com/user-attachments/assets/eacdff4b-f695-4f5a-b8cb-f72cbcc72200)


```sql
create table Members(MemberID INTEGER, MemberName TEXT, JoinDate DATE);
```

**Output:**

![Screenshot 2025-05-03 142802](https://github.com/user-attachments/assets/a93c1e12-f324-4c16-b7f7-e271e9f9135a)


**Question 2**
---
![Screenshot 2025-05-03 142818](https://github.com/user-attachments/assets/b32194e6-da49-4661-852e-e79060b8e975)


```sql
CREATE TABLE Invoices 
(InvoiceID INTEGER UNIQUE,
InvoiceDate DATE,
DueDate DATE CHECK(DueDate>InvoiceDate),
Amount REAL CHECK(Amount>0)
);
```

**Output:**

![Screenshot 2025-05-03 142835](https://github.com/user-attachments/assets/256326cf-d4d3-45fc-94a7-3a37347d7a94)


**Question 3**
---

![Screenshot 2025-05-03 142850](https://github.com/user-attachments/assets/9659acc3-debf-49f8-812d-384267cf1b95)

```sql
CREATE TABLE Invoices 
(InvoiceID INTEGER UNIQUE,
InvoiceDate DATE,
DueDate DATE CHECK(DueDate>InvoiceDate),
Amount REAL CHECK(Amount>0)
);
```

**Output:**

![Screenshot 2025-05-03 142905](https://github.com/user-attachments/assets/7b269592-9848-4bf2-b5f4-3fcef8f392bb)


**Question 4**
---
![Screenshot 2025-05-03 142921](https://github.com/user-attachments/assets/285029e6-5876-49b8-92d9-c2aa00670ea5)


```sql
ALTER TABLE Companies RENAME name TO first_name;
ALTER TABLE Companies ADD COLUMN mobilenumber number;
ALTER TABLE Companies ADD COLUMN DOB Date;
ALTER TABLE Companies ADD COLUMN State varchar(30);
```

**Output:**
![Screenshot 2025-05-03 142936](https://github.com/user-attachments/assets/82d20f19-0d9a-45a8-b1b7-6a8ae1bfb5f7)



**Question 5**
---

![Screenshot 2025-05-03 142952](https://github.com/user-attachments/assets/862a87af-9d15-469d-9f26-9852144d55da)

```sql
insert into Products (ProductID,ProductName,Price,Stock) select ProductID,ProductName,Price,Stock from Discontinued_products;
```

**Output:**
![Screenshot 2025-05-03 143010](https://github.com/user-attachments/assets/1d3bca42-afe3-4094-a736-8928718f93a1)



**Question 6**
---
![Screenshot 2025-05-03 143024](https://github.com/user-attachments/assets/e49edbad-b73e-418e-8e4f-9cbe178bf252)


```sql
ALTER TABLE Companies ADD COLUMN designation varchar(50);
ALTER TABLE Companies ADD COLUMN net_salary number;
ALTER TABLE Companies ADD COLUMN dob date;
```

**Output:**

![Screenshot 2025-05-03 143039](https://github.com/user-attachments/assets/60ab5e62-bc0d-4a1f-bdfb-6242584f131c)


**Question 7**
---
![Screenshot 2025-05-03 143053](https://github.com/user-attachments/assets/2847178e-2dc2-42c7-8674-e3fca018236f)


```sql
CREATE TABLE Shipments
(ShipmentID INTEGER PRIMARY KEY,
ShipmentDate DATE,
SupplierID INTEGER,
OrderID INTEGER,
FOREIGN KEY(SupplierID) REFERENCES Suppliers,
FOREIGN KEY(OrderID) REFERENCES Orders
);
```

**Output:**
![Screenshot 2025-05-03 143106](https://github.com/user-attachments/assets/b2ec90bb-0abd-444b-b82d-a460b2b46cc2)



**Question 8**
---
![Screenshot 2025-05-03 143121](https://github.com/user-attachments/assets/3f872695-f2ea-4f49-befd-7b517fb3c371)

```sql
CREATE TABLE jobs 
(job_id INTEGER,
job_title VARCHAR(30) DEFAULT "",
min_salary NUMBER DEFAULT '8000',
max_salary NUMBER DEFAULT NULL
);
```

**Output:**
![Screenshot 2025-05-03 143138](https://github.com/user-attachments/assets/38079b69-5e18-467a-a416-bd51a3cbc2cb)



**Question 9**
---

![Screenshot 2025-05-03 143156](https://github.com/user-attachments/assets/50f76b29-a036-4971-9780-034dee11f745)

```sql
INSERT INTO Customers(CustomerID,Name,Address,City,ZipCode) VALUES (306,"Diana Prince","Themyscira",NULL,NULL);
INSERT INTO Customers(CustomerID,Name,Address,City,ZipCode) VALUES (307,"Bruce Wayne","Wayne Manor","Gotham",10007);
INSERT INTO Customers(CustomerID,Name,Address,City,ZipCode) VALUES (308,"Peter Parker","Queens",NULL,11375);
```

**Output:**
![Screenshot 2025-05-03 143210](https://github.com/user-attachments/assets/e00edfb1-d7d1-4330-a014-a67bb7447fdb)



**Question 10**
---
![Screenshot 2025-05-03 143232](https://github.com/user-attachments/assets/7895c4b7-a6f1-40cc-9264-f20019f40617)


```sql
INSERT INTO Customers(CustomerID,Name,Address,City,ZipCode) VALUES (301,"Michael Jordan","123 Maple St","Chicago",60616);
```

**Output:**

![Screenshot 2025-05-03 143246](https://github.com/user-attachments/assets/c0e071a8-627a-4b22-80c3-0207272e3b42)



## RESULT
Thus, the SQL queries to implement different types of constraints and DDL commands have been executed successfully.
