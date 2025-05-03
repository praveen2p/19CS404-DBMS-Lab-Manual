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

**Question 1**
--
![Screenshot 2025-05-03 151519](https://github.com/user-attachments/assets/87dacc21-1899-4442-bb4f-b64c883b1b8e)

```sql
select Specialty,Gender,count(DoctorID) as TotalDoctors from DOCTORS
group by Specialty,Gender;
```

**Output:**

![Screenshot 2025-05-03 151536](https://github.com/user-attachments/assets/943f5676-8af4-4443-bb63-c1c43d3049f3)


**Question 2**
---
![Screenshot 2025-05-03 151551](https://github.com/user-attachments/assets/90f4a81c-8dc6-409e-a799-413d84f73313)


```sql
select substr(Date,1,7) as Month, count(RecordID) as TotalRecords from medicalrecords
group by Month;
```

**Output:**

![Screenshot 2025-05-03 151604](https://github.com/user-attachments/assets/c59507dc-207f-410e-9402-f4e7e8e8e173)


**Question 3**
---
![Screenshot 2025-05-03 151618](https://github.com/user-attachments/assets/910f0ae7-e131-423b-a473-36ee3e3e7d34)


```sql
select PatientID, count(AppointmentID)as TotalAppointments from appointments
group by patientid;
```

**Output:**

![Screenshot 2025-05-03 151631](https://github.com/user-attachments/assets/de2437b5-f8b4-4478-b3ec-c631d18bbe6e)


**Question 4**
---
![Screenshot 2025-05-03 151646](https://github.com/user-attachments/assets/48a8c353-bf07-4020-8ba5-f5edb6278802)


```sql
select sum(inventory)as total_available_amount from fruits
where price>0.5;
```

**Output:**

![Screenshot 2025-05-03 151659](https://github.com/user-attachments/assets/18350e60-e2d0-4074-b30f-8bf2630955ec)


**Question 5**
---
![Screenshot 2025-05-03 151713](https://github.com/user-attachments/assets/4ff8b806-a7ac-4938-98c5-9b2df858d601)


```sql
select MIN(purch_amt) as MINIMUM from orders;
```

**Output:**

![Screenshot 2025-05-03 151731](https://github.com/user-attachments/assets/04c241db-ef88-4583-ac9a-849d8aaec1ca)


**Question 6**
---
![Screenshot 2025-05-03 151745](https://github.com/user-attachments/assets/23be9808-2263-4ad9-9c13-2fce1be447a4)


```sql
select Count(id) as COUNT from employee
where age>32;
```

**Output:**
![Screenshot 2025-05-03 151759](https://github.com/user-attachments/assets/920e09b6-13a1-42f0-adfa-a98eddc46737)


**Question 7**
---
![Screenshot 2025-05-03 151813](https://github.com/user-attachments/assets/f4059dd1-bbc3-4283-9d42-fae941bdea90)


```sql
select count(customer_id) as COUNT from customer;
```

**Output:**

![Screenshot 2025-05-03 151827](https://github.com/user-attachments/assets/bf1006d8-5cd3-48c6-a627-088a8630a2ba)


**Question 8**
---
![Screenshot 2025-05-03 151845](https://github.com/user-attachments/assets/09a01647-20d1-427c-a967-316b3c997101)

```sql
select city,sum(income) as Income from employee
group by city
having Income>200000;
```

**Output:**

![Screenshot 2025-05-03 151901](https://github.com/user-attachments/assets/f090414c-503a-4011-9862-98670b89faaa)


**Question 9**
---
![Screenshot 2025-05-03 151915](https://github.com/user-attachments/assets/772d1121-9de1-4f19-af6a-38d04c1709ad)


```sql
select jdate, SUM(workhour) from employee1
group by jdate
having sum(workhour)>40;
```

**Output:**

![Screenshot 2025-05-03 151928](https://github.com/user-attachments/assets/4374c9f7-ef63-4c3e-b6fc-37499302db54)


**Question 10**
---
![Screenshot 2025-05-03 151952](https://github.com/user-attachments/assets/8e454306-fcf3-4dfb-95a5-75e9416a45b5)


```sql
select jdate,AVG(workhour) from employee1
group by jdate
having avg(workhour)<10;
```

**Output:**

![Screenshot 2025-05-03 152007](https://github.com/user-attachments/assets/ef07ac1b-8e51-4284-912c-e17d999aba8e)


## RESULT
Thus, the SQL queries to implement aggregate functions, GROUP BY, and HAVING clause have been executed successfully.
