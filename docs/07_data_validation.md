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

---

## Advanced Duplicate Check — Business-Level Transactions

**Purpose**

Even if transaction IDs are unique, duplicate payments can still occur due to
system retries or ingestion errors. To detect this, a business-level duplicate
check was performed using:

- user_id
- merchant_id
- transaction_time
- amount

This helps identify transactions that appear identical from a business
perspective but may have different transaction IDs.

**Result**

No business-level duplicate transactions detected.

**Conclusion**

Transaction records appear consistent and no duplicate payment events were found.

---

## Step 3 — Transaction Amount Validation

### Objective
Validate financial transaction values to ensure that the dataset does not
contain impossible or unrealistic payment data.

The following checks were performed:

- Negative transaction amounts
- Zero-value transactions
- Transaction amount distribution

---

### Negative Transaction Check

Checked whether any transactions contain negative payment amounts.

**Result:**  
0 rows found.

**Interpretation:**  
No negative transaction amounts were detected.  
This confirms that the dataset does not contain invalid financial records
caused by ingestion or processing errors.

---

### Zero-Value Transaction Check

Checked whether any transactions were recorded with zero value.

**Result:**  
0 rows found.

**Interpretation:**  
No zero-value transactions exist in the dataset.  
This indicates that all recorded payments represent actual financial activity.

---

### Transaction Amount Distribution

Reviewed the minimum, maximum, and average transaction values.

**Result:**

Minimum Transaction Value: 10.00  
Maximum Transaction Value: 499,604.35  
Average Transaction Value: 3,832.78

**Interpretation:**  
The transaction values appear realistic for a digital payments platform.
The dataset does not show abnormal or suspicious transaction values
that would indicate major data quality issues.

---
