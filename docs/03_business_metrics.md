# 📊 FlowPay — Business Metrics (Updated Logic)

This section defines the **core metrics framework** used to evaluate:

- Platform performance  
- Financial health  
- User behavior  
- Fraud risk  

The goal is not just to calculate numbers, but to build a **structured measurement system** that answers:

> **Is the platform growing? Is it reliable? Where is risk coming from?**

---

# 🏗️ 1. Platform Metrics

These metrics measure **scale, growth, and core system performance**.

---

## 🔹 Transaction Volume (Payment Attempts)

**Definition:** Total number of payment attempts  
**Formula:**  
`COUNT(*) WHERE status IN ('SUCCESS','FAILED')`

**Why it matters:**

- Measures actual platform usage  
- Excludes refunds (post-transaction event)  
- Represents real user interaction with the payment system  

---

## 🔹 Gross Payment Volume (GPV)

**Definition:** Total value of successful transactions  
**Formula:**  
`SUM(amount WHERE status = 'SUCCESS')`

**Why it matters:**

- Indicates total money flowing through the platform  
- Core revenue-driving metric  

---

## 🔹 Net Processed Value

**Definition:** Value retained after refunds  
**Formula:**  
`SUCCESS AMOUNT - REFUNDED AMOUNT`

**Why it matters:**

- Reflects **actual realized value**  
- Accounts for post-transaction reversals  

---

## 🔹 Success Rate

**Definition:** Percentage of successful payment attempts  
**Formula:**  
`SUCCESS / (SUCCESS + FAILED)`

**Why it matters:**

- Core indicator of **payment system reliability**  
- Measures clean execution of transactions  

> ⚠️ Note: Fraud is excluded from denominator to focus on **system performance**, not risk filtering.

---

## 🔹 Failure Rate

**Definition:** Percentage of failed payment attempts  
**Formula:**  
`FAILED / (SUCCESS + FAILED)`

**Why it matters:**

- Highlights:
  - System issues  
  - Payment gateway failures  
  - user/payment friction  

---

## 🔹 Active Users

**Definition:** Users who completed at least one successful transaction  
**Formula:**  
`COUNT(DISTINCT user_id WHERE status = 'SUCCESS')`

**Why it matters:**

- Measures **true engaged users**  
- Filters out unsuccessful or incomplete interactions  

---

## 🔹 Average Transaction Value (ATV)

**Definition:** Average value per successful transaction  
**Formula:**  
`AVG(amount WHERE status = 'SUCCESS')`

**Why it matters:**

- Indicates typical transaction size  
- Helps understand user spending behavior  

---

# 🔁 2. Post-Transaction Metrics

These metrics measure **what happens after a successful payment**.

---

## 🔹 Refund Rate

**Definition:** Percentage of successful transactions that were refunded  
**Formula:**  
`REFUNDED / SUCCESS`

**Why it matters:**

- Indicates post-payment issues such as:
  - Merchant/service problems  
  - Order cancellations  
  - Duplicate or incorrect transactions  

> ⚠️ Important: Refunds are calculated only against successful transactions, not total attempts.

---

## 🔹 Refund Value

**Definition:** Total amount refunded  
**Formula:**  
`SUM(amount WHERE status = 'REFUNDED')`

**Why it matters:**

- Measures **financial impact of reversals**  
- Critical for revenue tracking  

---

# 🚨 3. Risk Metrics

These metrics track **fraud exposure and system risk**.

---

## 🔹 Fraud Rate

**Definition:** Percentage of fraudulent transactions among payment attempts  
**Formula:**  
`FRAUDULENT / (SUCCESS + FAILED)`

**Why it matters:**

- Measures fraud prevalence at the **attempt level**  
- Helps assess platform vulnerability  

---

## 🔹 Fraud Exposure

**Definition:** Total value of fraudulent transactions  
**Formula:**  
`SUM(amount WHERE status = 'FRAUDULENT')`

**Why it matters:**

- Indicates potential **financial risk**  
- Helps prioritize fraud prevention efforts  

---

## 🔹 Fraud Detection Rate

**Definition:** Percentage of fraudulent transactions that are reported or detected  
**Formula:**  
`fraud_reports / FRAUDULENT`

**Why it matters:**

- Evaluates effectiveness of fraud detection systems  

---

## 🔹 High-Risk Transaction Rate

**Definition:** Percentage of transactions flagged as risky  
**Formula:**  
`risky_transactions / (SUCCESS + FAILED)`

**Why it matters:**

- Early warning signal for emerging fraud patterns  

---

# 👤 4. User Behavior Metrics

These metrics help understand **usage patterns and anomalies**.

---

## 🔹 Transactions per User

**Definition:** Average number of payment attempts per user  
**Formula:**  
`(SUCCESS + FAILED) / TOTAL USERS`

**Why it matters:**

- Identifies:
  - Power users  
  - Casual users  

---

## 🔹 Average Spend per User

**Definition:** Average successful transaction value per user  
**Formula:**  
`TOTAL SUCCESS AMOUNT / TOTAL USERS`

**Why it matters:**

- Identifies **high-value users**  
- Shows revenue concentration  

---

## 🔹 Device Count per User

**Definition:** Number of devices used per user  
**Formula:**  
`COUNT(DISTINCT device_id per user)`

**Why it matters:**

- High values may indicate:
  - Normal multi-device usage  
  - Suspicious activity (account sharing / spoofing)  

---

## 🔹 Velocity Transactions

**Definition:** Number of transactions within a short time window  

**Why it matters:**

- Detects rapid activity patterns  
- Strong indicator of **fraud or bot behavior**  

---

# 💳 5. Payment Performance Metrics

These metrics evaluate **system performance across payment channels**.

---

## 🔹 Failure Rate by Payment Method

**Definition:** Failure percentage per payment method  
**Formula:**  
`FAILED / (SUCCESS + FAILED) BY payment_method`

**Why it matters:**

- Identifies weak or unreliable payment channels  

---

## 🔹 Success Rate by Payment Method

**Definition:** Success percentage per payment method  
**Formula:**  
`SUCCESS / (SUCCESS + FAILED) BY payment_method`

**Why it matters:**

- Highlights high-performing payment options  

---

## 🔹 Retry Rate

**Definition:** Percentage of failed transactions followed by retry  
**Formula:**  
`retry_transactions / failed_transactions`

**Why it matters:**

- Measures user friction and persistence  

---

## 🔹 Success After Retry Rate

**Definition:** Percentage of retries that succeed  
**Why it matters:**

- Distinguishes:
  - Temporary failures (network/system)  
  - Permanent failures (user/payment issues)  

---

# 🏪 6. Merchant Metrics

These metrics evaluate **merchant contribution and risk**.

---

## 🔹 GPV per Merchant

**Definition:** Total transaction value per merchant  
**Formula:**  
`SUM(amount WHERE status = 'SUCCESS') GROUP BY merchant`

**Why it matters:**

- Identifies revenue-driving merchants  

---

## 🔹 Fraud Rate per Merchant

**Definition:** Fraud percentage per merchant  
**Formula:**  
`FRAUDULENT / (SUCCESS + FAILED) BY merchant`

**Why it matters:**

- Detects merchants linked to risky activity  

---

## 🔹 Refund Rate per Merchant

**Definition:** Refund percentage per merchant  
**Formula:**  
`REFUNDED / SUCCESS BY merchant`

**Why it matters:**

- Indicates:
  - Service quality issues  
  - Operational inefficiencies  

---

# 🎯 Important Interpretation Notes

- **SUCCESS →** Money successfully processed  
- **FAILED →** Payment attempt failed (no money movement)  
- **REFUNDED →** Money reversed after success  
- **FRAUDULENT →** Risk signal (not always completed transaction)  

👉 Key Principle:

- **Payment Metrics → SUCCESS + FAILED**  
- **Financial Metrics → SUCCESS + REFUNDED**  
- **Risk Metrics → FRAUDULENT analyzed separately**  

---

# 🔥 One-Line Summary

These metrics create a **clean, structured measurement system** that separates **payment performance, financial flow, and risk**, enabling accurate analysis of platform growth, reliability, and vulnerabilities.
