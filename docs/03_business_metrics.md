# 📊 FlowPay — Business Metrics Framework

This document defines the core metrics used to evaluate:

* Platform performance
* Financial health
* User behavior
* Fraud and risk exposure

The goal is to build a **structured measurement system** that answers:

> *How is the platform performing, where is revenue being lost, and where does risk originate?*

---

## 🧠 Metric Design Principle

To avoid mixing different stages of the transaction lifecycle, metrics are divided into three layers:

### 🔹 1. Platform Reality (Attempt-Level Outcomes)

Includes:

* SUCCESS
* FAILED
* FRAUDULENT

👉 Represents what happens when users attempt transactions

---

### 🔹 2. Financial Flow (Money Movement)

Includes:

* SUCCESS
* REFUNDED

👉 Represents how money is processed and reversed

---

### 🔹 3. Risk Signals

Includes:

* FRAUDULENT
* Behavioral risk indicators

👉 Represents fraud exposure and suspicious activity

---

# 🏗️ 1. Platform Metrics (Core Performance)

### 🔹 Transaction Volume (Payment Attempts)

**Definition:** Total number of payment attempts

**Formula:**

```
COUNT(*) WHERE status IN ('SUCCESS','FAILED','FRAUDULENT')
```

**Why it matters:**

* Measures real platform usage
* Represents all user interactions

---

### 🔹 Gross Payment Volume (GPV)

**Definition:** Total value of successful transactions

**Formula:**

```
SUM(amount WHERE status = 'SUCCESS')
```

**Why it matters:**

* Core revenue-driving metric
* Reflects money processed through the platform

---

### 🔹 Net Processed Value

**Definition:** Value retained after refunds

**Formula:**

```
SUCCESS AMOUNT - REFUNDED AMOUNT
```

**Why it matters:**

* Shows actual realized revenue
* Accounts for post-payment leakage

---

### 🔹 Success Rate

**Definition:** Percentage of successful transactions

**Formula:**

```
SUCCESS / (SUCCESS + FAILED + FRAUDULENT)
```

**Why it matters:**

* Measures overall platform efficiency
* Key indicator of user experience

---

### 🔹 Failure Rate

**Definition:** Percentage of failed transactions

**Formula:**

```
FAILED / (SUCCESS + FAILED + FRAUDULENT)
```

**Why it matters:**

* Indicates system or payment issues
* Major driver of revenue loss

---

### 🔹 Fraud Rate

**Definition:** Percentage of fraudulent transactions

**Formula:**

```
FRAUDULENT / (SUCCESS + FAILED + FRAUDULENT)
```

**Why it matters:**

* Measures platform-level risk exposure
* Helps track fraud trends

---

### 🔹 Average Transaction Value (ATV)

**Definition:** Average value per successful transaction

**Formula:**

```
AVG(amount WHERE status = 'SUCCESS')
```

**Why it matters:**

* Indicates user spending behavior
* Helps segment high vs low value transactions

---

### 🔹 Active Users

**Definition:** Users with at least one successful transaction

**Formula:**

```
COUNT(DISTINCT user_id WHERE status = 'SUCCESS')
```

**Why it matters:**

* Measures true engagement
* Filters out failed-only users

---

# 🔁 2. Financial Metrics (Post-Transaction)

### 🔹 Refund Rate

**Definition:** Percentage of successful transactions that were refunded

**Formula:**

```
REFUNDED / SUCCESS
```

**Why it matters:**

* Captures post-payment issues
* Indicates merchant/service quality

---

### 🔹 Refund Value

**Definition:** Total refunded amount

**Formula:**

```
SUM(amount WHERE status = 'REFUNDED')
```

**Why it matters:**

* Measures financial impact of reversals

---

### 🔹 Revenue Retention Rate

**Definition:** Percentage of revenue retained after refunds

**Formula:**

```
NET VALUE / GPV
```

**Why it matters:**

* Final indicator of revenue efficiency
* Connects directly to business profitability

---

# 🚨 3. Risk Metrics (Fraud & Exposure)

### 🔹 Fraud Exposure (Value)

**Definition:** Total value of fraudulent transactions

**Formula:**

```
SUM(amount WHERE status = 'FRAUDULENT')
```

**Why it matters:**

* Quantifies financial risk

---

### 🔹 Fraud Detection Rate

**Definition:** Percentage of fraudulent transactions that are reported

**Formula:**

```
fraud_reports / FRAUDULENT
```

**Why it matters:**

* Evaluates detection effectiveness
* Connects model output with real-world reporting

---

### 🔹 Risk Distribution (Model Output)

**Definition:** Distribution of users across risk levels

**Output:**

* 🟢 Low Risk
* 🟡 Medium Risk
* 🚨 High Risk

**Why it matters:**

* Enables targeted risk strategies
* Balances fraud control and conversion

---

# 👤 4. User Behavior Metrics

### 🔹 Transactions per User

**Formula:**

```
TOTAL TRANSACTIONS / TOTAL USERS
```

**Why it matters:**

* Identifies power vs casual users

---

### 🔹 Average Spend per User

**Formula:**

```
TOTAL SUCCESS AMOUNT / TOTAL USERS
```

**Why it matters:**

* Highlights high-value users

---

### 🔹 Device Count per User

**Formula:**

```
COUNT(DISTINCT device_id)
```

**Why it matters:**

* High values may indicate suspicious behavior

---

### 🔹 Velocity Indicator

**Definition:** Rapid transactions within short intervals

**Why it matters:**

* Strong fraud signal
* Detects abnormal activity bursts

---

### 🔹 Retry Behavior

**Definition:** User attempts after failed transactions

**Key Metrics:**

* Retry Count
* Retry Success Rate

**Why it matters:**

* Indicates friction in payment flow
* Can signal both genuine intent and abuse

---

# 💳 5. Payment Performance Metrics

### 🔹 Failure Rate by Payment Method

```
FAILED / TOTAL ATTEMPTS BY payment_method
```

### 🔹 Success Rate by Payment Method

```
SUCCESS / TOTAL ATTEMPTS BY payment_method
```

### 🔹 Failure Rate by Device / City

**Why it matters:**

* Identifies system inefficiencies
* Detects regional or platform issues

---

# 🏪 6. Merchant Metrics

### 🔹 GPV per Merchant

```
SUM(amount WHERE status = 'SUCCESS')
```

### 🔹 Fraud Rate per Merchant

```
FRAUDULENT / TOTAL ATTEMPTS
```

### 🔹 Refund Rate per Merchant

```
REFUNDED / SUCCESS
```

**Why it matters:**

* Identifies high-risk merchants
* Supports targeted monitoring

---

# 🎯 Key Interpretation Notes

* **SUCCESS** → Completed transactions
* **FAILED** → Unsuccessful attempts
* **FRAUDULENT** → Risk-flagged transactions
* **REFUNDED** → Post-payment reversals

---

# 🧠 Final Principle

* Platform Metrics → Measure system performance
* Financial Metrics → Measure money flow
* Risk Metrics → Measure fraud exposure

👉 These layers must **never be mixed**, ensuring accurate interpretation.

---

# 🔥 One-Line Summary

This framework separates transaction outcomes, financial impact, and risk signals to provide a clear, structured view of platform performance, revenue efficiency, and fraud exposure.

