# Financials_DB-
Project Introduction

The Financial Management System is a database project created using MySQL to manage banking information easily. It stores customer details, bank accounts, transactions, loans, and payment information in an organized way. All the tables are connected to maintain correct and accurate data. The system helps track deposits, withdrawals, and loan payments efficiently. This project shows how databases are used to handle banking operations in a simple and structured manner.

Key Objectives

To store and manage customer banking details in a structured database.
To maintain account information and track account balances.
To record and monitor financial transactions such as deposits, withdrawals, and transfers.
To manage loan details and interest information of customers.
To track loan repayment and payment history efficiently.
To maintain data accuracy using relationships between tables.
To provide an organized system for handling banking operations easily.

This Project Is Useful

Helps store customer and banking details in one place.
Makes managing account and balance information easy.
Tracks deposits, withdrawals, and transfers properly.
Helps manage customer loan details.
Keeps record of loan payments and repayment history.
Reduces manual work and data errors.
Provides an organized and easy way to handle financial records.

Sample Use Case

 A bank employee can add and manage customer account details in the system.
 Customers can deposit or withdraw money, and the transactions are recorded automatically.
 The bank can provide loans to customers and store loan information securely.
 Loan payments made by customers can be tracked easily.
 The system helps the bank monitor customer financial activities in an organized way.

Queries Classification

Simple Queries:
 		 SELECT, WHERE, ORDER BY
Intermediate Queries: 
		GROUP BY, HAVING, LIMITS, JOINS
Advanced Queries: 
		CTE, Sub query, Window function ,
		 Functions , Store procedures, Views
     
Contstraints:

Unique Key:
A unique key in MySQL is a single field or combination of fields that ensure all values going to store into the column will be unique. It means a column cannot stores duplicate 
Primary Key:
MySQL primary key is a single or combination of the field, which is used to identify each record in a table uniquely. If the column contains primary key constraints, then it cannot be null or empty. A table may have duplicate columns, but it can contain only one primary key. It always contains unique value into a column.
Foreign Key:
The foreign key is used to link one or more than one table together. It is also known as the referencing key. A foreign key matches the primary key field of another table. It means a foreign key field in one table refers to the primary key field of the other table. It identifies each row of another table uniquely that maintains the referential integrity in MySQL.
NOT NULL:
The NOT NULL constraint is a column constraint that ensures values stored in a column are not NULL.

Main Database tables
Customers:	Customer details, Personal information, Contact details
Accounts:	Bank account, Account type, Balance details
Transactions:	Deposit, Withdrawal, Money transfer
Loans	:Loan details, Loan type, Interest rate
Payments:	Loan repayment, Payment mode, Payment history

Dataset Information

Select * from customers;
<img width="657" height="379" alt="Screenshot 2026-02-19 190852" src="https://github.com/user-attachments/assets/68421dbe-0d92-4004-9d31-c1efee451ed8" />


select * from accounts;

<img width="481" height="393" alt="Screenshot 2026-02-19 191202" src="https://github.com/user-attachments/assets/2d3d5666-8cad-4f69-a4f4-2791d5e87e97" />

select * from transactions;
<img width="607" height="439" alt="image" src="https://github.com/user-attachments/assets/1b224f44-1ddf-47ed-8924-2b0138fbca22" />

select * from loans;
<img width="644" height="415" alt="Screenshot 2026-02-19 191430" src="https://github.com/user-attachments/assets/21eae349-ffdf-46a7-94c3-6fca7060a707" />

select * from payments;
<img width="610" height="420" alt="Screenshot 2026-02-19 191554" src="https://github.com/user-attachments/assets/e4125e06-00cd-4965-83be-c30f3543e9dc" />

Create table

<img width="709" height="418" alt="Screenshot 2026-02-19 192126" src="https://github.com/user-attachments/assets/5da1266a-2218-4c8a-9c16-b8e9b34b75f1" />

<img width="932" height="667" alt="Screenshot 2026-02-19 192319" src="https://github.com/user-attachments/assets/bc00947d-6f44-4b5e-b052-a76a86bbd0cc" />

What is WHERE Condition in MySQL?

The WHERE condition in MySQL is used to filter records from a table based on a specific condition. It helps to display only the required data instead of showing all records.
SELECT * 
FROM customers
WHERE city = 'New York';

<img width="602" height="254" alt="Screenshot 2026-02-19 192718" src="https://github.com/user-attachments/assets/5d08a164-3c17-4d01-adfc-600d7ba583c2" />


What is GROUP BY in MySQL?

The GROUP BY clause in MySQL is used to group rows that have the same values in a column.
It is mainly used with aggregate functions like COUNT(), SUM(), AVG(), MAX(), and MIN().
SELECT account_type, SUM(balance) AS total_balance
FROM accounts
GROUP BY account_type;


<img width="552" height="258" alt="image" src="https://github.com/user-attachments/assets/33c5254a-5df0-4539-9138-be419421c564" />

What is HAVING in MySQL?

The HAVING clause in MySQL is used to filter grouped data after using the GROUP BY clause.
SELECT account_type, SUM(balance) AS total_balance
FROM accounts
GROUP BY account_type
HAVING SUM(balance) > 100000;

<img width="553" height="287" alt="Screenshot 2026-02-19 193252" src="https://github.com/user-attachments/assets/20bcfa08-4bd9-4ddc-b860-eb28020a30c6" />

What is ORDER BY in MySQL?

The ORDER BY clause in MySQL is used to sort the result data in ascending or descending order.
SELECT * 
FROM customers
ORDER BY full_name ASC;

<img width="734" height="338" alt="image" src="https://github.com/user-attachments/assets/17d10938-05ff-4bed-ba88-814a48e5c76a" />

What is JOIN in MySQL?

A JOIN in MySQL is used to combine data from two or more tables based on a related column.
SELECT c.full_name, t.transaction_type, t.amount
FROM customers c
JOIN accounts a 
ON c.customer_id = a.customer_id
JOIN transactions t
ON a.account_id = t.account_id;

<img width="536" height="417" alt="image" src="https://github.com/user-attachments/assets/29a141f4-836c-46c1-aee6-3c9b15044f0e" />

What is CTE in MySQL?

CTE means Common Table Expression.
It is a temporary result table that you can use inside a query to make complex queries easier to understand.
WITH customer_balance AS (
    SELECT customer_id, balance
    FROM accounts
)
SELECT c.full_name, cb.balance
FROM customers c
JOIN customer_balance cb
ON c.customer_id = cb.customer_id;

<img width="752" height="357" alt="image" src="https://github.com/user-attachments/assets/858a5661-fca9-4f94-a12f-edabc6bf683e" />

What is CASE Function in MySQL?

The CASE function in MySQL is used to apply conditions and return different values based on those conditions.
SELECT payment_id, mode,
CASE
    WHEN mode = 'UPI' THEN 'Digital Payment'
    WHEN mode = 'Online' THEN 'Internet Banking'
    ELSE 'Offline Payment'
END AS payment_type
FROM payments;

<img width="984" height="435" alt="Screenshot 2026-02-19 194430" src="https://github.com/user-attachments/assets/0664d675-2c21-4cf0-8c5e-16d29025c557" />

What is VIEW in MySQL?

A VIEW in MySQL is a virtual table created using a SQL query.

 It does not store data physically
 It shows data from one or more tables
 It works like a saved SELECT query

Table → stores real data
View → shows data using stored query
CREATE VIEW customer_orders AS
SELECT 
    c.customer_name,
    o.product,
    o.amount
FROM customers c
JOIN orders o
ON c.customer_id = o.customer_id;
What is Stored Procedure in MySQL? (Simple Words)

A Stored Procedure is a saved SQL program inside MySQL.
It is a group of SQL statements
Stored inside database
Executed whenever needed
Query → runs one time
Stored Procedure → saved & reused many times
It works like a function inside database.
DELIMITER //

CREATE PROCEDURE CustomerOrderDetails()
BEGIN
    SELECT 
        c.customer_name,
        o.product,
        o.amount
    FROM customers c
    JOIN orders o
    ON c.customer_id = o.customer_id;
END //

DELIMITER ;

What is Function in MySQL? 

A Function in MySQL is a stored program that returns a single value.

 It performs calculation or logic
 Takes input value
 Always gives one output

Stored Procedure → returns table/result
Function → returns one value

DELIMITER //

CREATE FUNCTION TotalCustomerAmount(cid INT)
RETURNS INT
DETERMINISTIC
BEGIN
    DECLARE total INT;

    SELECT SUM(amount)
    INTO total
    FROM orders
    WHERE customer_id = cid;

    RETURN total;
END //

DELIMITER ;

 What is Window Function in MySQL? (Simple Words)

A Window Function is used to perform calculation across rows without grouping the data.

 It works on a group of rows called a window
 But does not combine rows like GROUP BY
 Shows result for each row

 Project Conclusion

This project helps in managing and analyzing financial and sales data in an organized way. It allows easy tracking of customer orders and business performance using MySQL queries. The system provides useful insights for better decision-making. It also improves data accuracy and reporting. Overall, the project shows how databases support efficient business management.



























