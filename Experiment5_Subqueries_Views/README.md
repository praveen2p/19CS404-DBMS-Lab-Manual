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

**Question 1**
--
![Screenshot 2025-05-03 153501](https://github.com/user-attachments/assets/ef6f51c4-2f40-40ea-a8df-8863b41b131f)


```sql
SELECT o.ord_no, o.purch_amt, o.ord_date, o.salesman_id
FROM orders o
JOIN salesman s ON o.salesman_id = s.salesman_id
WHERE s.commission = (
    SELECT MAX(commission)
    FROM salesman
);

```

**Output:**
![Screenshot 2025-05-03 153515](https://github.com/user-attachments/assets/e69ac2d2-f6e2-4150-96d5-8869e0003063)



**Question 2**
---
![Screenshot 2025-05-03 153533](https://github.com/user-attachments/assets/3ed7a830-ff54-4342-816c-b6cb657425ae)


```sql
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

![Screenshot 2025-05-03 153545](https://github.com/user-attachments/assets/0d11b297-3233-485c-b729-d1b50db98520)


**Question 3**
---
![Screenshot 2025-05-03 153558](https://github.com/user-attachments/assets/e37073e7-c271-4399-b534-4ce1aadff57e)


```sql
SELECT grade, COUNT(*) 
FROM customer 
WHERE grade > (
    SELECT AVG(grade) 
    FROM customer 
    WHERE city = 'New York'
)
GROUP BY grade;

```

**Output:**

![Screenshot 2025-05-03 153611](https://github.com/user-attachments/assets/96220ffd-8b4d-4b36-b118-5c093fbd65a2)


**Question 4**
---
![Screenshot 2025-05-03 153628](https://github.com/user-attachments/assets/0d20396c-3498-431f-9cd7-d3d2f8eef8ad)


```sql
SELECT student_name, grade
FROM GRADES g
WHERE grade = (
    SELECT MAX(grade)
    FROM GRADES
    WHERE subject = g.subject
);

```

**Output:**

![Screenshot 2025-05-03 153641](https://github.com/user-attachments/assets/f0c7364a-a0ee-4898-ae9b-a5f473d3dde9)


**Question 5**
---
![Screenshot 2025-05-03 153657](https://github.com/user-attachments/assets/65aa7842-0a95-4aaf-b9cd-4535ff02f636)


```sql
SELECT s.salesman_id, s.name
FROM salesman s
JOIN customer c ON s.salesman_id = c.salesman_id
GROUP BY s.salesman_id, s.name
HAVING COUNT(c.customer_id) > 1;

```

**Output:**

![Screenshot 2025-05-03 153710](https://github.com/user-attachments/assets/a51f8316-0f25-4cc7-8848-901da4abd72f)


**Question 6**
---
![Screenshot 2025-05-03 153722](https://github.com/user-attachments/assets/b7987ea2-90b2-47c9-a0ab-52b2ea555800)


```sql
SELECT *
FROM CUSTOMERS
WHERE ADDRESS = 'Delhi' AND AGE < 30
order by id asc;
```

**Output:**
![Screenshot 2025-05-03 153736](https://github.com/user-attachments/assets/e80216f4-0486-47cc-9982-99adca47ce5f)



**Question 7**
---
![Screenshot 2025-05-03 154554](https://github.com/user-attachments/assets/b1582985-38f4-49c4-8bd6-262a137a15a2)


```sql
SELECT *
FROM Employee
WHERE age < (
    SELECT AVG(age)
    FROM Employee
    WHERE income > 250000
);

```

**Output:**

![Screenshot 2025-05-03 154607](https://github.com/user-attachments/assets/90ae3b9f-7ff7-4a75-8fbb-fc97633ff2cc)


**Question 8**
---

![Screenshot 2025-05-03 154621](https://github.com/user-attachments/assets/51788f34-0907-4983-8f98-7913c31e70e3)

```sql
SELECT name, city
FROM customer
WHERE city IN (
    SELECT city
    FROM customer
    WHERE id IN (3, 7)
);

```

**Output:**

![Screenshot 2025-05-03 154636](https://github.com/user-attachments/assets/57d04770-abce-4fb1-8524-773c06577796)


**Question 9**
---
![Screenshot 2025-05-03 154648](https://github.com/user-attachments/assets/5a760c7c-6120-43d9-921f-c752fcec2883)


```sql
SELECT *
FROM Medications
WHERE dosage = (
    SELECT MAX(dosage)
    FROM Medications
);

```

**Output:**

![Screenshot 2025-05-03 154700](https://github.com/user-attachments/assets/162a0c9c-65f9-47d1-85ac-d2a54064cfb0)


**Question 10**
---
![Screenshot 2025-05-03 154714](https://github.com/user-attachments/assets/b86afdc2-efce-48be-9e73-f5c4c2bef50a)


```sql
SELECT o.ord_no, o.purch_amt, o.ord_date, o.customer_id, o.salesman_id
FROM orders o
JOIN salesman s ON o.salesman_id = s.salesman_id
WHERE s.city = 'New York';

```

**Output:**
![Screenshot 2025-05-03 154726](https://github.com/user-attachments/assets/69baf715-5d17-438f-9308-113379618e10)



## RESULT
Thus, the SQL queries to implement subqueries and views have been executed successfully.
