# RDBMS - Relational Database Management System

- Dr. E.F Codd proposed Relational model of Database in 1970
- Relational model 
  - Collection of Objects or relationals 
  - Set of Operators to act on the relations 
  - Data integrity for accurcy and consistency 


## Entity
- Singular, Unique Name
- Uppercase
- Soft box 
- Synonym in parentheses 

## Attribute


--

### Primary Key
- Unique and not Null

## SQL Developement Environment

- SQL Developer 
- SQL * Plus CLI

## Oracle Database
- Manageability
- Higher Availability
- Performance 
- Security 
- Inforation Integration 



``` 
SELECT *| {DISTINCT} column [alias],...
```


```
SELECT * 
FROM department;
```

- SQL statement are not case sensitive, can be entered on one or more lines



- SQLDeveloper
  - GUI based
  - designed for oracle but can be connected to any database that support Java 
- SQL*Plus
  - CLI

JDBC (Java Database Connector) like ODBC (Open Database Connector) for connecting different databases.

- Arithmetic Operators 
  - mathematical Operator
- Operator Precedence
  - BODMAS
- Defining a Null
  - Null is a values that is unavailable, unassigned , unknown or inapplicable
  - Null is not saeas zero or blanck
- Using Column Aliases 
- Concatenation Operator
  - Links columns or character strings to other coloumns by ** || **
- Using Literal character strings   
  - `last_name || ' is a ' || designation
- ALternative Quote (q)
  - Specify your own quotation mark delimiter 
  - ` SELECT department_name || q' [Department's Manager Id:]' || manager_id AS "Deparment & Manager" 
- Duplicate Rows
  - Dont show duplicate and rows 



### Describe 
- Shares structure of Table 


# LAB 
Open `https://livesql.oracle.com/` for Online SQL Query 


```
SELECT last_name AS name, commission_pct comm
FROM employees;
```

```
SELECT department_id from hr.departments;
```

## DATE 
DD-MON-RR 
-------------

## WHERE
For selecting data from schema

```
SELECT department_id 
FROM employees
WHERE department_id = 90;
```
`%` for multiple character
`_` for single character

```
WHERE first_name LIKE 'B%' ;
```
--------------

## Key Points

- NADRA is uing Oracle
- `--department_id = 90` is for comments


------------------

![RDBMS](https://camo.githubusercontent.com/07f303f1ee9c2683d9326158d709f0e9e8f44c2c37afd55f67385618642ad0ea/68747470733a2f2f766572746162656c6f2e636f6d2f626c6f672f776861742d69732d7264626d732f312e706e67)

---


<details><summary>CLICK ME</summary>
<p>

#### We can hide anything, even code!

```ruby
   puts "Hello World"
```

</p>
</details>