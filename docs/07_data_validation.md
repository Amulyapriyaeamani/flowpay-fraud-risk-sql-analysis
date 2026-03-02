# Data Validation Report
FlowPay Risk & Payment Analysis Project

This document records the results of data validation checks performed after loading the dataset into PostgreSQL.  
The goal is to ensure data integrity, correct relationships between tables, and identify potential issues before analysis.

---

# Step 1 — Validate Table Relationships (Data Integrity)

## Objective
Verify that all transactions correctly reference valid entities in the database.

In real-world systems, data pipelines sometimes fail and create **orphan records** — records that reference data that does not exist.  
This step ensures the relational integrity of the database.

The following relationships were validated:

- Transactions → Users
- Transactions → Merchants
- Transactions → Devices

---

## Check 1 — Transactions referencing non-existing users

**Purpose**

Ensure every transaction belongs to a valid user in the `users` table.

**Expected Result**

0 records.

**Result**

0 issues found.

**Conclusion**

All transactions correctly reference valid users.  
Data integrity between `transactions` and `users` tables is maintained.

---

## Check 2 — Transactions referencing non-existing merchants

**Purpose**

Ensure every transaction is linked to a valid merchant.

**Expected Result**

0 records.

**Result**

0 issues found.

**Conclusion**

All transactions correctly reference valid merchants.  
Relationship integrity between `transactions` and `merchants` tables is valid.

---

## Check 3 — Transactions referencing non-existing devices

**Purpose**

Verify that every transaction is associated with a valid device.

**Expected Result**

0 records.

**Result**

0 issues found.

**Conclusion**

All transactions correctly reference existing devices.  
No orphan device references were found.

---

# Overall Data Integrity Status

All foreign key relationships between the core transactional tables are valid.  
No orphan records were detected.

This indicates that:
- Data ingestion was successful
- Table relationships were properly defined
- The dataset is reliable for further analysis

---

# Why This Validation Matters

In real payment systems, broken relationships can lead to:

- Incorrect fraud detection
- Revenue miscalculations
- Inaccurate user activity analysis
- Reporting errors

Performing this validation ensures the analysis is based on **trusted data**.

---

# Step 2 — Check Duplicate Records

## Objective
Detect duplicate records that may have been created during data ingestion or pipeline failures.

Duplicate records can cause:
- Incorrect revenue calculations
- Inflated transaction counts
- Incorrect fraud analysis

The following tables were validated:
- transactions
- users
- fraud_reports

---

## Duplicate Check — Transactions

**Purpose**

Verify that each transaction ID appears only once.

**Result**

No duplicate transactions detected.

**Conclusion**

Primary key integrity is maintained for the transactions table.

---

## Duplicate Check — Users

**Purpose**

Ensure that each user record is unique.

**Result**

No duplicate users detected.

**Conclusion**

User records are unique and consistent.

---

## Duplicate Check — Fraud Reports

**Purpose**

Ensure fraud reports are not duplicated for the same transaction.

**Result**

No duplicate fraud reports detected.

**Conclusion**

Fraud reporting system data appears consistent.

---

# Duplicate Validation Summary

All tables passed duplicate validation checks.  
No ingestion or pipeline duplication issues were found.
