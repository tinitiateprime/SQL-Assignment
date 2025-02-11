# Data Setup

## Dept Data 
```sql
INSERT INTO employees.dept (deptno, dname, loc)
VALUES
(10, 'ACCOUNTING', 'NEW YORK'),
(20, 'RESEARCH', 'DALLAS'),
(30, 'SALES', 'CHICAGO'),
(40, 'OPERATIONS', 'BOSTON');
```
## Sal Grade
```sql
INSERT INTO employees.salgrade (grade, losal, hisal)
VALUES
(1, 700, 1200),
(2, 1201, 1400),
(3, 1401, 2000),
(4, 2001, 3000),
(5, 3001, 5000);
```
## Projects
```sql
INSERT INTO employees.projects (projectno, budget, monthly_commission)
VALUES
(100, 50000.00, 500.00),
(200, 75000.00, 750.00),
(300, 100000.00, 1000.00),
(400, 25000.00, 250.00),
(500, 150000.00, 1500.00);
```
## Emp
```sql
DO $$
DECLARE 
    i INT;
BEGIN
    FOR i IN 1..1000 LOOP
        INSERT INTO employees.emp (empno, ename, job, mgr, hiredate, sal, commission, deptno)
        VALUES 
        (
            i, 
            'EMP' || i, 
            CASE WHEN i % 3 = 0 THEN 'MANAGER' ELSE 'CLERK' END, 
            CASE WHEN i > 1 THEN i - 1 ELSE NULL END, 
            DATE '2020-01-01' + (i % 365), 
            1000 + (i * 10), 
            CASE WHEN i % 5 = 0 THEN 500 ELSE NULL END, 
            CASE WHEN i % 4 = 0 THEN 10 WHEN i % 3 = 0 THEN 20 WHEN i % 2 = 0 THEN 30 ELSE 40 END
        );
    END LOOP;
END $$;
```
## Emp_projects
```sql
DO $$
DECLARE 
    i INT;
    emp_id INT;
    proj_id INT;
BEGIN
    FOR i IN 1..1000 LOOP
        emp_id := i;
        proj_id := (i % 5 + 1) * 100; -- Match project numbers 100, 200, etc.
        
        INSERT INTO employees.emp_projects (emp_projectno, empno, projectno, start_date, end_date)
        VALUES 
        (
            i, 
            emp_id, 
            proj_id, 
            DATE '2021-01-01' + (i % 30), 
            DATE '2023-01-01' + (i % 30)
        );
    END LOOP;
END $$;

```