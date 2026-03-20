# 📊 FlowPay — Business Metrics (Final Correct Version)

This section defines the **core metrics framework** used to evaluate:

- Platform performance  
- Financial health  
- User behavior  
- Fraud risk  

The goal is not just to calculate numbers, but to build a **structured measurement system** that answers:

> **Is the platform growing? What actually happens to transactions? Where is risk coming from?**

---

# 🧠 Metric Design Principle (VERY IMPORTANT)

To avoid mixing different stages of the transaction lifecycle, metrics are divided into **three layers**:

### 🔹 1. Platform Reality (Attempt-Level Outcomes)
Includes:  
`SUCCESS + FAILED + FRAUDULENT`

👉 Represents **what actually happens when users attempt payments**

---

### 🔹 2. Financial Flow (Money Movement)
Includes:  
`SUCCESS + REFUNDED`

👉 Represents **how money flows and gets reversed**

---

### 🔹 3. Risk Signals
Includes:  
`FRAUDULENT`

👉 Represents **fraud exposure and suspicious activity**

---

# 🏗️ 1. Platform Metrics (Platform Reality Layer)

These metrics measure **scale, growth, and real transaction outcomes**.

---

## 🔹 Transaction Volume (Payment Attempts)

**Definition:** Total number of payment attempts  

**Formula:**  
`COUNT(*) WHERE status IN ('SUCCESS','FAILED','FRAUDULENT')`

**Why it matters:**

- Measures actual platform usage  
- Excludes refunds (post-transaction event)  
- Represents real user interaction  

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

## 🔹 Success Rate (Platform-Level)

**Definition:** Percentage of successful outcomes out of all attempts  

**Formula:**  
`SUCCESS / (SUCCESS + FAILED + FRAUDULENT)`

**Why it matters:**

- Measures **real-world success probability**  
- Reflects overall platform outcome, not just system performance  

---

## 🔹 Failure Rate

**Definition:** Percentage of failed payment attempts  

**Formula:**  
`FAILED / (SUCCESS + FAILED + FRAUDULENT)`

**Why it matters:**

- Highlights:
  - System issues  
  - Payment friction  
  - Bank or network failures  

---

## 🔹 Fraud Rate

**Definition:** Percentage of fraudulent transactions among all attempts  

**Formula:**  
`FRAUDULENT / (SUCCESS + FAILED + FRAUDULENT)`

**Why it matters:**

- Measures **platform-level risk exposure**  
- Includes fraud as part of real transaction outcomes  

---

## 🔹 Active Users

**Definition:** Users who completed at least one successful transaction  

**Formula:**  
`COUNT(DISTINCT user_id WHERE status = 'SUCCESS')`

**Why it matters:**

- Measures **true engaged users**  
- Filters out unsuccessful interactions  

---

## 🔹 Average Transaction Value (ATV)

**Definition:** Average value per successful transaction  

**Formula:**  
`AVG(amount WHERE status = 'SUCCESS')`

**Why it matters:**

- Indicates typical transaction size  
- Helps understand user spending behavior  

---

# 🔁 2. Financial Metrics (Post-Transaction Layer)

These metrics measure **what happens after a successful payment**.

---

## 🔹 Refund Rate

**Definition:** Percentage of successful transactions that were refunded  

**Formula:**  
`REFUNDED / SUCCESS`

**Why it matters:**

- Captures post-payment issues such as:
  - Merchant/service problems  
  - Order cancellations  
  - Incorrect transactions  

> ⚠️ Refunds are calculated only against successful transactions because refunds occur after payment completion.

---

## 🔹 Refund Value

**Definition:** Total amount refunded  

**Formula:**  
`SUM(amount WHERE status = 'REFUNDED')`

**Why it matters:**

- Measures **financial impact of reversals**  
- Critical for revenue tracking  

---

# 🚨 3. Risk Metrics (Fraud Layer)

These metrics track **fraud exposure and detection effectiveness**.

---

## 🔹 Fraud Exposure

**Definition:** Total value of fraudulent transactions  

**Formula:**  
`SUM(amount WHERE status = 'FRAUDULENT')`

**Why it matters:**

- Indicates **potential financial risk**  
- Helps prioritize fraud prevention  

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
`risky_transactions / (SUCCESS + FAILED + FRAUDULENT)`

**Why it matters:**

- Early warning signal for emerging fraud patterns  

---

# 👤 4. User Behavior Metrics

These metrics help understand **usage patterns and anomalies**.

---

## 🔹 Transactions per User

**Definition:** Average number of payment attempts per user  

**Formula:**  
`(SUCCESS + FAILED + FRAUDULENT) / TOTAL USERS`

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
  - Suspicious behavior  

---

## 🔹 Velocity Transactions

**Definition:** Number of transactions within a short time window  

**Why it matters:**

- Detects rapid activity patterns  
- Strong indicator of fraud or bot behavior  

---

# 💳 5. Payment Performance Metrics

These metrics evaluate **performance across payment channels**.

---

## 🔹 Failure Rate by Payment Method

**Formula:**  
`FAILED / (SUCCESS + FAILED + FRAUDULENT) BY payment_method`

---

## 🔹 Success Rate by Payment Method

**Formula:**  
`SUCCESS / (SUCCESS + FAILED + FRAUDULENT) BY payment_method`

---

## 🔹 Retry Rate

**Formula:**  
`retry_transactions / failed_transactions`

---

## 🔹 Success After Retry Rate

**Definition:** Percentage of retries that succeed  

---

# 🏪 6. Merchant Metrics

These metrics evaluate **merchant contribution and risk**.

---

## 🔹 GPV per Merchant

**Formula:**  
`SUM(amount WHERE status = 'SUCCESS') GROUP BY merchant`

---

## 🔹 Fraud Rate per Merchant

**Formula:**  
`FRAUDULENT / (SUCCESS + FAILED + FRAUDULENT) BY merchant`

---

## 🔹 Refund Rate per Merchant

**Formula:**  
`REFUNDED / SUCCESS BY merchant`

---

# 🎯 Important Interpretation Notes

- **SUCCESS →** Payment completed successfully  
- **FAILED →** Payment attempt failed  
- **FRAUDULENT →** Transaction flagged as risky (after attempt)  
- **REFUNDED →** Post-transaction reversal  

---

# 🧠 Key Principle (FINAL CLARITY)

- **Platform Metrics → SUCCESS + FAILED + FRAUDULENT**  
- **Financial Metrics → SUCCESS + REFUNDED**  
- **Risk Metrics → FRAUDULENT analyzed within platform outcomes**  

---

# 🔥 One-Line Summary

This framework separates **platform outcomes, financial flow, and risk signals**, ensuring that metrics reflect **real transaction behavior, monetary impact, and fraud exposure without mixing lifecycle stages**.
