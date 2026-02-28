# FlowPay — Dataset Schema

This project simulates a production-style data model for a digital payments platform.
The schema is designed to reflect how fintech companies store and analyze transaction activity, user behavior, merchant performance, and fraud investigations.

The dataset supports platform health analysis, fraud detection, and risk modeling.

---

# Platform Data Model

The FlowPay ecosystem connects users, merchants, devices, and transactions.

Users → Devices → Transactions → Merchants → Fraud Reports

This structure allows the analytics team to analyze:

* User transaction behavior
* Merchant performance
* Device usage patterns
* Fraud investigations

---

# Table Relationships

The project dataset contains six tables.

users (1) → (many) transactions
merchants (1) → (many) transactions
users (1) → (many) devices
transactions (1) → (optional) fraud_reports
transactions (1) → (optional) refunds

These relationships enable multi-table analysis using joins, which is common in real analytics workflows.

---

# Dataset Scale

The dataset simulates a growing fintech startup environment.

Users: ~25,000
Merchants: ~3,000
Devices: ~40,000
Transactions: ~2.4 million

Time Period Covered
January 2024 → December 2024

This scale enables realistic transaction analysis, behavioral analysis, and fraud pattern detection.

---

# Table Overview

## Users

Represents customers using the FlowPay platform.

Grain
One row = one user account.

Key Columns

* user_id
* signup_date
* city
* age
* kyc_verified
* risk_score
* signup_channel

This table is used to analyze user growth, demographics, and risk behavior.

---

## Merchants

Represents businesses accepting payments through FlowPay.

Grain
One row = one merchant.

Key Columns

merchant_id
merchant_name
merchant_category
city
onboard_date
risk_level

This table enables merchant performance and fraud risk analysis by category.

---

## Devices

Represents devices used by users to access the platform.

Grain
One row = one device linked to a user.

Key Columns

device_id
user_id
device_type
device_brand
first_seen
last_seen

This table helps analyze device switching patterns and suspicious behavior.

---

## Transactions

This is the core dataset used for most analyses.

Grain
One row = one payment attempt.

Key Columns

transaction_id
user_id
merchant_id
device_id
transaction_time
amount
payment_method
status
ip_city

This table supports analysis such as:

* Platform transaction trends
* Payment performance
* User activity patterns
* Fraud detection

---

## Fraud Reports

Represents transactions that were flagged or investigated for fraud.

Grain
One row = one fraud investigation linked to a transaction.

Key Columns

fraud_id
transaction_id
fraud_type
reported_time
fraud_score
investigation_status

This table is used to analyze fraud patterns and risk signals.

---

## Refunds

Represents refund events associated with transactions.

Grain
One row = one refund record.

Key Columns

refund_id
transaction_id
refund_amount
refund_reason
refund_time

This table helps analyze refund trends and financial impact.

---

# Why This Schema Matters

This data model allows the analysis to simulate real-world fintech analytics tasks such as:

* Investigating fraud patterns
* Monitoring platform health
* Evaluating merchant risk
* Analyzing user behavior
* Detecting suspicious activity
* Understanding payment system performance

The schema reflects how transactional platforms structure data for analytics and risk monitoring.
