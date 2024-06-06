﻿# INFORMATICA


## Images

<div align="center">
  <img src="img/1 (1).png" >
  <img src="img/1 (12.png" >
</div>

## SQL Code

```sql
-- 29.5.24 --

ALTER TABLE customer (
    customer_id INT PRIMARY KEY,
    cust_first_name VARCHAR2(30),
    cust_last_name VARCHAR2(30),
    cust_phone_no INT,
    cust_email_id VARCHAR2(50),
    order_id INT
);

ALTER TABLE customerdata RENAME COLUMN cust_full_name TO cust_first_name;

INSERT INTO customer (customer_id, cust_first_name, cust_last_name, cust_phone_no, cust_email_id, order_id) 
VALUES (1, 'John', 'Doe', 1234567890, 'johndoe@example.com', 1001);

INSERT INTO customer (customer_id, cust_first_name, cust_last_name, cust_phone_no, cust_email_id, order_id) 
VALUES (2, 'Jane', 'Smith', 2345678901, 'janesmith@example.com', 1002);

INSERT INTO customer (customer_id, cust_first_name, cust_last_name, cust_phone_no, cust_email_id, order_id) 
VALUES (3, 'Mike', 'Johnson', 3456789012, 'ikejohnson@example.com', 1003);

INSERT INTO customer (customer_id, cust_first_name, cust_last_name, cust_phone_no, cust_email_id, order_id) 
VALUES (4, 'Sara', 'Brown', 4567890123, 'arabrown@example.com', 1004);

INSERT INTO customer (customer_id, cust_first_name, cust_last_name, cust_phone_no, cust_email_id, order_id) 
VALUES (5, 'David', 'Williams', 5678901234, 'davidwilliams@example.com', 1005);

CREATE TABLE customerdata (
    customer_id INT PRIMARY KEY,
    cust_full_name VARCHAR2(30),
    cust_last_name VARCHAR2(30),
    cust_phone_no INT,
    cust_email_id VARCHAR2(50),
    order_id INT
);

SELECT * FROM customerdata;

TRUNCATE TABLE customerdata;

-- 31.5.24 --

CREATE TABLE customerdetails (
    customer_id INT PRIMARY KEY,
    cust_full_name VARCHAR2(30),
    cust_phone_no INT,
    cust_email_id VARCHAR2(50),
    order_id INT
);

SELECT * FROM customer;
SELECT * FROM customerdata;
SELECT * FROM customerdetails;

TRUNCATE TABLE customerdetails;

-- 3.6.24 --

CREATE TABLE org_employee_dept1(
    emp_id INT, 
    emp_full_name VARCHAR2(50), 
    emp_salary INT, 
    dept_id INT
);

CREATE TABLE org_employee_dept2(
    emp_id INT, 
    emp_full_name VARCHAR2(50), 
    emp_salary INT, 
    dept_id INT
);

CREATE TABLE org_employee_dept3(
    emp_id INT, 
    emp_full_name VARCHAR2(50), 
    emp_salary INT, 
    dept_id INT
);

CREATE TABLE org_employee_default(
    emp_id INT, 
    emp_full_name VARCHAR2(50), 
    emp_salary INT, 
    dept_id INT
);

COMMIT;

SELECT * FROM org_employee_dept3;
SELECT * FROM employees WHERE department_id = 30;
SELECT * FROM employees;

TRUNCATE TABLE org_employee_default;

-- 4.6.2024 --

CREATE TABLE org_employee_data(
    emp_id INT, 
    emp_full_name VARCHAR2(50), 
    emp_salary INT, 
    dept_id INT
);

ALTER TABLE org_employee_data MODIFY emp_full_name VARCHAR2(100);

SELECT * FROM org_employee_data;

-- 5.6.2024 Aggregator Transformation --

CREATE TABLE dept_salary(
    dept_id INT, 
    sum_dept_salary INT
);

SELECT * FROM dept_salary
ORDER BY dept_id ASC;

SELECT * FROM employees;

-- Joining, Master, Full Details --

CREATE TABLE SUBJECTS(
    SUBJECT_ID INT, 
    SUBJECT_NAME VARCHAR(30)
);

INSERT INTO SUBJECTS VALUES (1, 'MATHS');
INSERT INTO SUBJECTS VALUES (2, 'CHEMISTRY');
INSERT INTO SUBJECTS VALUES (3, 'PHYSICS');

TRUNCATE TABLE subjects;

CREATE TABLE STUDENTS(
    STUDENT_ID INT, 
    SUBJECT_ID INT
);

INSERT INTO STUDENTS VALUES (10, 1);
INSERT INTO STUDENTS VALUES (20, 2);
INSERT INTO STUDENTS VALUES (30, NULL);

SELECT * FROM students_rec;

TRUNCATE TABLE students_rec;

CREATE TABLE STUDENT_REC(
    SUBJECT_ID INT,
    STUDENT_ID INT,
    SUBJECT_NAME VARCHAR(30)
);

-- Rank Transformation --

CREATE TABLE employee_rank(
    emp_id INT, 
    dept_id INT, 
    salary INT, 
    rank INT
);

SELECT * FROM employee_rank;

-- Sequence Transformation --

CREATE TABLE employee_sequence_number(
    sr_no INT,
    emp_id INT, 
    dept_id INT, 
    salary INT
);

SELECT * FROM employee_sequence_number;
