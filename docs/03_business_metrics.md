# FlowPay — Business Metrics Definition

To evaluate platform performance and detect fraud risk, the analytics team tracks a set of key business metrics. These metrics help monitor platform growth, payment reliability, and suspicious activity patterns.

The metrics are grouped into three categories:

* Platform Metrics
* Risk Metrics
* User Behavior Metrics

---

# 1. Platform Metrics

These metrics measure the overall health and performance of the FlowPay platform.

### Transaction Volume

Definition
Total number of transactions processed within a given time period.

Why it matters
Transaction volume indicates platform growth and adoption. Monitoring trends helps identify seasonal spikes, sudden drops, or abnormal activity.

Example analysis
Daily / weekly / monthly transaction trends.

---

### Transaction Success Rate

Definition
Percentage of transactions successfully completed.

Formula
Success Rate = Successful Transactions / Total Transactions

Why it matters
A declining success rate may indicate:

* Payment infrastructure issues
* Bank declines
* System instability
* Fraud prevention triggers blocking transactions

---

### Revenue Processed

Definition
Total payment value successfully processed through the platform.

Why it matters
This metric represents the economic activity handled by the platform and helps measure business scale.

It also helps identify:

* High-value transaction patterns
* Revenue concentration among merchants

---

### Active Users

Definition
Number of unique users who performed at least one transaction during a specific period.

Why it matters
Active users indicate engagement and platform stickiness.

This metric helps identify:

* Growth in adoption
* Retention trends
* Power users driving platform activity

---

# 2. Risk Metrics

These metrics help the Risk and Fraud teams understand exposure to fraudulent activity.

### Fraud Rate

Definition
Percentage of transactions identified as fraudulent.

Formula
Fraud Rate = Fraudulent Transactions / Total Transactions

Why it matters
Even small increases in fraud rate can significantly impact financial losses and user trust.

Monitoring fraud rate helps identify:

* Emerging fraud trends
* Weak points in the payment system
* High-risk transaction segments

---

### Fraud by Merchant Category

Definition
Fraud rate segmented by merchant category.

Why it matters
Certain categories are more vulnerable to fraud, such as:

* Gaming
* Digital goods
* High-frequency transaction businesses

Identifying these patterns helps prioritize risk monitoring.

---

### Fraud Loss

Definition
Total monetary value lost due to fraudulent transactions.

Why it matters
This metric measures the financial impact of fraud on the platform and helps justify investment in fraud detection systems.

---

### High-Risk Users

Definition
Users identified as potentially suspicious based on behavioral signals such as:

* Rapid transaction activity
* Multiple device usage
* High-value transactions shortly after signup
* High transaction failure rate

Why it matters
Identifying risky users early allows the platform to implement risk controls such as:

* Transaction monitoring
* Temporary limits
* Additional verification checks

---

# 3. User Behavior Metrics

These metrics analyze how users interact with the platform and help detect unusual activity patterns.

### Average Transactions per User

Definition
Average number of transactions performed by a user during a defined period.

Why it matters
Helps identify:

* Highly active users
* Normal transaction patterns
* Potential bot-like activity

---

### Average Spend per User

Definition
Average transaction value per user.

Why it matters
Understanding spending behavior helps detect anomalies such as:

* Sudden spikes in transaction amounts
* High-value suspicious transactions

---

### Device Switching Behavior

Definition
Number of different devices used by a single user over time.

Why it matters
Frequent device changes can indicate potential fraud or account compromise.

This metric is particularly useful when analyzing:

* Account takeover fraud
* Suspicious login activity

---

### Velocity Transactions

Definition
Multiple transactions executed within a very short time window.

Example
More than 5 transactions within 3 minutes.

Why it matters
Velocity patterns are a common fraud signal used by fintech platforms to detect automated or suspicious payment activity.

---

# How These Metrics Support the Investigation

These metrics collectively help the analytics team:

* Monitor platform health
* Identify operational issues
* Detect fraud patterns
* Understand user behavior
* Provide actionable recommendations to reduce risk

They will be used throughout the analysis in the following stages:

Platform analysis
Payment performance investigation
Merchant risk analysis
User behavior analysis
Fraud detection modeling
