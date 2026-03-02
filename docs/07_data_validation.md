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

## Duplicate Validation Summary

All tables passed duplicate validation checks.  
No ingestion or pipeline duplication issues were found.

---

# Advanced Duplicate Check — Business-Level Transactions

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

# Step 3 — Transaction Amount Validation

## Objective
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

# Step 4 — Device Data Quality Validation

This step evaluates the quality and reliability of device-related data, which is important for fraud detection and behavioral analysis.

Device signals are commonly used in payment platforms to detect suspicious activity such as account takeover or automated transactions.

## 1. Transactions Missing Device Information

Check performed to identify transactions where `device_id` is not recorded.

**Result:**
- 5105 transactions were found without device information.

**Interpretation:**
- This is not necessarily an error. In real payment systems, this can occur due to:
  - Guest checkout scenarios
  - Device tracking limitations
  - Certain payment methods not capturing device data
  - Logging or instrumentation gaps
- However, transactions without device data reduce the ability to perform device-based fraud analysis.

## 2. Devices Linked to Multiple Users

This check verifies whether a single device is associated with multiple users, which could indicate suspicious behavior such as shared devices or account misuse.

**Result:**
- No devices were found linked to multiple users.

**Interpretation:**
- Device ownership appears consistent in the dataset, indicating that device-to-user relationships are clean and reliable.
- This improves confidence in device-based fraud signals.

## 3. Users With High Number of Devices

This analysis checks whether some users are associated with an unusually large number of devices, which can be a potential fraud indicator.

**Result:**
- Total users analyzed: 25,000
- No users were found with more than 5 devices.

**Interpretation:**
- User-device distribution appears normal.
- There are no immediate signals of suspicious multi-device activity.
- This suggests the dataset reflects realistic user behavior patterns.

---

# Step 5 — Fraud Data Consistency Validation

This step validates whether fraud investigation data aligns correctly with transaction records.

Ensuring consistency between these tables is important because fraud analysis relies on accurate relationships between transaction outcomes and investigation records.

## 1. Fraud Reports for Transactions Marked SUCCESS

This check identifies whether fraud investigations exist for transactions that are still marked as SUCCESS.

**Result:**

0 rows returned.

**Interpretation:**

No fraud reports were found for transactions marked as successful. This indicates that fraud investigations are properly aligned with transaction status in the dataset.

The fraud reporting process appears consistent.

## 2. Transactions Marked FRAUDULENT Without Fraud Reports

This check verifies whether transactions labeled as FRAUDULENT have a corresponding fraud investigation record.

**Result:**

0 rows returned.

**Interpretation:**

All transactions marked as fraudulent have associated fraud reports. This confirms that fraud events are properly tracked and recorded in the system.

## 3. Fraud Score Validation

This check ensures fraud scores fall within the expected range defined in the schema (0–100).

**Result:**

0 rows returned.

**Interpretation:**

All fraud scores are within the valid range. This confirms that the fraud scoring system is functioning correctly and the dataset does not contain invalid values.

## Conclusion

Fraud data appears consistent across the transactions and fraud reports tables. No mismatches or invalid fraud scores were detected.

This indicates that the dataset is reliable for further fraud analysis and investigation.
