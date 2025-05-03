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
**Question 1**
--
![Screenshot 2025-05-03 145707](https://github.com/user-attachments/assets/2f8a415b-d015-4fc6-8820-ad528df1696e)


```sql
UPDATE EMPLOYEES
SET email='not available',commission_pct=0.55 where department_id= 110;
```

**Output:**

![Screenshot 2025-05-03 145728](https://github.com/user-attachments/assets/82766e0a-2627-4c04-902f-c3745b1e8e92)


**Question 2**
---
![Screenshot 2025-05-03 145915](https://github.com/user-attachments/assets/f1d42597-005c-494a-a8a4-fd7dea328133)


```sql
update Products
set quantity=1.1*quantity;
```

**Output:**

![Screenshot 2025-05-03 145929](https://github.com/user-attachments/assets/aa577aaa-02f9-4d3c-b4c8-2c85c970d92c)


**Question 3**
---
![Screenshot 2025-05-03 145946](https://github.com/user-attachments/assets/8b6d70d7-bb02-4f47-8f75-7b6ddceaa474)


```sql
update employees
set email='Unavailable';
```

**Output:**

![Screenshot 2025-05-03 150029](https://github.com/user-attachments/assets/f791dffe-ca3b-477b-a726-b4c02d665fc0)


**Question 4**
---
![Screenshot 2025-05-03 150046](https://github.com/user-attachments/assets/c9e44e71-c6ab-469b-a816-c214b2f175d1)


```sql
update employees
set hire_date='2024-01-24' where department_id=50;
```

**Output:**
![Screenshot 2025-05-03 150104](https://github.com/user-attachments/assets/85841151-d4c8-494b-a8d3-07dc19832555)



**Question 5**
---

![Screenshot 2025-05-03 150121](https://github.com/user-attachments/assets/e0430b47-9c69-4185-b246-1fa7f6c875a5)

```sql
delete from customer
where GRADE<2;
```

**Output:**
![Screenshot 2025-05-03 150132](https://github.com/user-attachments/assets/786edc81-88cb-4db0-9fe6-008b80fe979c)


**Question 6**
---
![Screenshot 2025-05-03 150211](https://github.com/user-attachments/assets/675cc74e-096e-49b7-84bc-26f9cdc8c35b)


```sql
SELECT EMPID,EMPPOSITION,DATEOFJOINING,SALARY FROM EMPLOYEEPOSITION 
WHERE SALARY BETWEEN 50000 AND 100000;
```

**Output:**

![Screenshot 2025-05-03 150158](https://github.com/user-attachments/assets/d1bf9414-aa81-444a-8174-30558f4e8418)


**Question 7**
---
![Screenshot 2025-05-03 150211](https://github.com/user-attachments/assets/c58ab806-2488-472d-920d-1d2b55e495dc)


```sql
SELECT * FROM EMPLOYEEINFO WHERE EMPFNAME LIKE 'S%';
```

**Output:**
![Screenshot 2025-05-03 150224](https://github.com/user-attachments/assets/b831c3e4-2832-43f9-860c-192d8293caad)



**Question 8**
---

![Screenshot 2025-05-03 150236](https://github.com/user-attachments/assets/a7a43c3d-9187-4819-96d0-d2cb0bd95893)

```sql
SELECT ID,VALUE1,
CASE
WHEN VALUE1%2!=0 THEN 'Odd'
ELSE 'Even'
END AS parity
FROM Calculations;
```

**Output:**

![Screenshot 2025-05-03 150250](https://github.com/user-attachments/assets/404ae325-3a27-426a-a560-bf3cb492c038)

**Question 9**
---

![Screenshot 2025-05-03 150305](https://github.com/user-attachments/assets/17c78245-f83e-4c54-beeb-c3998382b36b)

```sql
SELECT CUSTOMER_ID,CUST_NAME,CITY,GRADE,SALESMAN_ID FROM CUSTOMER WHERE GRADE IS NULL;
```

**Output:**

![Screenshot 2025-05-03 150319](https://github.com/user-attachments/assets/30785337-5fd1-4c06-887a-d5b376ba4f6b)


**Question 10**
---
![Screenshot 2025-05-03 150340](https://github.com/user-attachments/assets/e578f6b9-7a87-4e4f-b8f4-64abe04d1751)


```sql
SELECT ID,ROUND(DECIMAL,3) AS rounded_value
FROM CALCULATIONS;
```

**Output:**

![Screenshot 2025-05-03 150353](https://github.com/user-attachments/assets/31b45624-e2cc-4e25-ae58-c0c0031e612e)


## RESULT
Thus, the SQL queries to implement DML commands have been executed successfully.
