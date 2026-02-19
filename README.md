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








