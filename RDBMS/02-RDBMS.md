# RDBMS
- SQL
- No SQL

# Data Manipulation Language

- DMLstatement is executed when 
  - Add new rows to Table
  - Modify
  - Remove

A **Transaction** Collection of DML statement that forms a logical unit of work


## INSERT Statement

- Add new rows to a table 

```sql 
INSERT INTO table [(solumn [, coloumn ...])]
VALUES      (value [, value ...]);
```
example

```sql
INSERT INTO hr.department (department_id, department_name, manager_id, location_id)
VALUES (70, 'Public Relations', 100, 1700);
```


## INSERTING Data

- Implicit
- Explicit


## Insert SPECIAL values

SYSDATA function records current data and time

```sql
INSERT INTO employees (employees_id, hire_data)
VALUES      (113, CURRENT DATE);

```

### INSERTing SPecific DATE and TIME 
```sql 
INSERT INTO employees (manager_id, hire_date)
VALUES      (119, TO_DATE ('FEB 2, 2002', 'MON DD, YYYY'));
```

## COPY ROWS from Another Table 

- Insert statement with subquery

```sql 
INSERT INTO sales_reps (id, name, salary, commission_pct)
    SELECT employees_id, last_name, salary, commission_pct
    FROM employees
    WHERE job_id LIKE '%REP%';
```

- Dont use `VALUES' clause 
- Match the number of coloumns in the INSERT clause to those in the subquery

## UPDATE statement


```sql
UPDATE  table 
SET     coloumn = value [, coloumn = value, ...]
[WHERE condition]
```

If no condition is given, change is appled on all field.

## COMMIT & ROLLBACK

- with `COMMIT` and `ROLLBACK` statement
  - Ensure data consistency
  - preview data changes before making changes permenent
  - group logically related operations

--
```sql
CREATE table hr_emp AS SELECT * FROM hr.employees;
```