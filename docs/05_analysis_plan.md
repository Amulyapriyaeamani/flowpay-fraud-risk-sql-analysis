# FlowPay — Analysis Plan
## Fraud & Payment Risk Investigation

This analysis follows a structured investigation similar to how analytics teams operate inside a digital payments company. The goal is to understand platform health, identify operational issues, and detect fraud patterns across users, merchants, and transactions.

---

## Investigation Approach

The analysis follows a layered investigation approach:

1. Understand overall platform performance and growth
2. Identify operational weaknesses in the payment system
3. Analyze merchant and user behavior
4. Detect fraud signals and suspicious patterns
5. Build a behavior-based risk scoring model

This approach mirrors how product, risk, and analytics teams investigate issues in real fintech platforms.

---

## SQL Techniques Used in the Analysis

The investigation will use advanced SQL techniques commonly used in analytics roles:

- Multi-table joins across users, transactions, merchants, and devices
- Common Table Expressions (CTEs) for step-by-step analysis
- Window functions for behavioral pattern detection
- Time-based analysis of transactions
- Aggregations and segmentation
- Fraud signal detection using transaction patterns

These techniques simulate real-world analytical workflows used in fintech analytics teams.

---

# 1. Platform Health Check

The first step is to evaluate the overall health and growth of the platform.

### Key Checks

- Monthly transaction volume trend
- Active users over time
- Revenue processed by month
- Transaction success vs failure rate
- Refund rate
- Payment method distribution (UPI, Wallet, Cards)

### Goal

Identify whether platform growth is stable and detect any unusual spikes or drops in activity.

### Business Value

Provides a high-level view of platform performance before deeper investigation begins.

---

# 2. Payment Performance Analysis

Next, the analysis focuses on how well the payment system is functioning.

### Key Checks

- Failure rate by payment method
- Failure rate by device type
- Failure rate by city
- Transaction outcomes across payment types
- High-value transaction success vs failure

### Goal

Detect operational issues such as payment gateway failures, bank declines, or system instability.

### Business Value

Helps the product and payments teams improve transaction reliability and user experience.

---

# 3. Merchant Risk Analysis

This stage focuses on identifying merchants associated with abnormal or risky activity.

### Key Checks

- Fraud rate by merchant
- Refund rate by merchant
- Fraud by merchant category
- High-risk merchant segments
- Revenue concentration across merchants

### Goal

Detect merchants that may be enabling fraudulent or suspicious activity.

### Business Value

Supports merchant monitoring, onboarding decisions, and risk control policies.

---

# 4. User Behavior Analysis

This section analyzes how users interact with the platform and identifies unusual behavior patterns.

### Key Checks

- Average transactions per user
- Average spend per user
- Device switching behavior
- Multi-city transaction activity
- Rapid transaction attempts (velocity patterns)
- High-value transaction users

### Goal

Understand behavioral patterns that may signal fraud or abnormal activity.

### Business Value

Helps define behavioral indicators used in fraud detection systems.

---

# 5. Fraud Detection Investigation

This stage focuses specifically on identifying fraud patterns in the dataset.

### Key Checks

- Fraud rate over time
- Fraud by payment method
- Fraud by merchant category
- Fraud by device type
- Fraud by geography
- Velocity fraud detection (rapid repeated transactions)

### Goal

Identify patterns and characteristics associated with fraudulent transactions.

### Business Value

Supports fraud monitoring strategies and helps risk teams improve detection mechanisms.

---

# 6. Risk Model — Behavior-Based Risk Scoring

In the final stage, a simple risk scoring framework will be developed using behavioral signals derived from transaction data.

### Risk Signals

Potential indicators used in the model include:

- High transaction velocity
- Multiple devices used by a user
- Transactions across multiple cities
- High refund activity
- Interaction with high-risk merchants
- Repeated failed transactions
- High-value transactions shortly after signup

### Output

Users and merchants will be assigned a **behavior-based risk score derived from transaction patterns** to identify potential fraud clusters and high-risk entities.

### Business Value

Demonstrates how analytical insights can evolve into risk models used by fraud and risk teams in real fintech companies.
