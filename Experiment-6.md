# EXPERIMENT - 6
### AIM :
1. Display empno, ename, deptno from employee table. Instead of display department numbers display the related department name (Use case function).
```sql
SELECT 
    EMPNO,
    ENAME,
    CASE 
        WHEN DEPTNO = 10 THEN 'RESEARCH'
        WHEN DEPTNO = 20 THEN 'ACCOUNTING'
        WHEN DEPTNO = 30 THEN 'SALES'
        WHEN DEPTNO = 40 THEN 'OPERATIONS'
    END AS DNAME
FROM EMPLOYEE;
```

2. Display your age in days.
```sql
SELECT DATEDIFF(CURDATE(), '2000-01-01') AS AGE_IN_DAYS;
```

3. Display your age in months.
```sql
SELECT TIMESTAMPDIFF(MONTH, '2000-01-01', CURDATE()) AS AGE_IN_MONTHS;
```

4. Display the current date as 15th August Friday Nineteen Ninety-Seven.
```sql
SELECT DATE_FORMAT(CURDATE(), '%D %M %W %Y');
```

5. Display the following output for each row from employee table.
   Scott has joined the company on Wednesday 13th August Nineteen Ninety
```sql
SELECT CONCAT(ENAME, ' has joined the company on ',
       DATE_FORMAT(HIREDATE, '%W %D %M %Y'))
FROM EMPLOYEE;
```

6. Find the date for nearest Saturday after current date.
```sql
SELECT DATE_ADD(CURDATE(), INTERVAL (7 - DAYOFWEEK(CURDATE()) + 7) % 7 DAY);
```

7. Display current time.
```sql
SELECT CURTIME();
```

8. Display the date three months Before the current date
```sql
SELECT DATE_SUB(CURDATE(), INTERVAL 3 MONTH);
```

9. Display those employees who joined in the company in the month of Dec.
```sql
SELECT *
FROM EMPLOYEE
WHERE MONTH(HIREDATE) = 12;
```

10. Display those employees whose first 2 characters from hire date -last 2 characters of salary.
```sql
SELECT *
FROM EMPLOYEE
WHERE LEFT(DAY(HIREDATE), 2) = RIGHT(SAL, 2);
```

11. Display those employees whose 10% of salary is equal to the year of joining.
```sql
SELECT *
FROM EMPLOYEE
WHERE (SAL * 0.10) = YEAR(HIREDATE);
```

12. Display those employees who joined the company before 15 of the months.
```sql
SELECT *
FROM EMPLOYEE
WHERE DAY(HIREDATE) < 15;
```

13. Display those employees who has joined before 15th of the month
```sql
SELECT *
FROM EMPLOYEE
WHERE DATE_FORMAT(HIREDATE, '%d') < 15;
```

14. Display those employees whose joining DATE is available in deptno
```sql
SELECT *
FROM EMPLOYEE
WHERE DAY(HIREDATE) = DEPTNO;
```







