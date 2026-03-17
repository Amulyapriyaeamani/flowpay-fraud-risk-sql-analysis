# 📊 FlowPay — Business Metrics

This section defines the core metrics used to evaluate **platform performance, financial health, user behavior, and fraud risk**.

The goal is not just to calculate numbers, but to create a **structured measurement system** that helps answer:

> *Is the platform growing? Is it reliable? Where is risk coming from?*

---

## 🏗️ 1. Platform Metrics

These metrics provide a high-level view of **overall platform performance and growth**.

### 🔹 Transaction Volume
- **Definition:** Total number of transactions processed  
- **Formula:** `COUNT(*)`  
- **Why it matters:**  
  Measures platform usage and growth over time  

---

### 🔹 Gross Payment Volume (GPV)
- **Definition:** Total value of successful transactions  
- **Formula:** `SUM(amount WHERE status = 'SUCCESS')`  
- **Why it matters:**  
  Indicates how much money is flowing through the platform  

---

### 🔹 Net Processed Value
- **Definition:** Value retained after refunds  
- **Formula:** `SUCCESS AMOUNT - REFUNDED AMOUNT`  
- **Why it matters:**  
  Reflects actual realized transaction value after reversals  

---

### 🔹 Success Rate
- **Definition:** Percentage of successful transactions  
- **Formula:** `SUCCESS / TOTAL TRANSACTIONS`  
- **Why it matters:**  
  Core indicator of **payment reliability and system performance**  

---

### 🔹 Failure Rate
- **Definition:** Percentage of failed transactions  
- **Formula:** `FAILED / TOTAL TRANSACTIONS`  
- **Why it matters:**  
  Highlights payment issues, system failures, or integration problems  

---

### 🔹 Refund Rate
- **Definition:** Percentage of successful transactions that were refunded  
- **Formula:** `REFUNDED / SUCCESSFUL TRANSACTIONS`  
- **Why it matters:**  
  Indicates post-payment issues such as:
  - Customer dissatisfaction  
  - Merchant issues  
  - Operational errors  

---

### 🔹 Active Users
- **Definition:** Unique users who performed transactions  
- **Formula:** `COUNT(DISTINCT user_id)`  
- **Why it matters:**  
  Measures user engagement and platform reach  

---

### 🔹 Average Transaction Value (ATV)
- **Definition:** Average value per successful transaction  
- **Formula:** `AVG(amount WHERE status = 'SUCCESS')`  
- **Why it matters:**  
  Helps understand typical transaction size and user spending behavior  

---

## 🚨 2. Risk Metrics

These metrics track **fraud exposure and risk concentration** across the platform.

---

### 🔹 Fraud Rate
- **Definition:** Percentage of transactions marked as fraud  
- **Formula:** `FRAUDULENT / TOTAL TRANSACTIONS`  
- **Why it matters:**  
  Measures overall fraud prevalence on the platform  

---

### 🔹 Fraud Exposure
- **Definition:** Total value of fraudulent transactions  
- **Formula:** `SUM(amount WHERE status = 'FRAUDULENT')`  
- **Why it matters:**  
  Indicates potential financial risk and impact  

---

### 🔹 Fraud Detection Rate
- **Definition:** Percentage of fraudulent transactions that are reported  
- **Formula:** `fraud_reports / FRAUDULENT TRANSACTIONS`  
- **Why it matters:**  
  Evaluates effectiveness of fraud detection and reporting systems  

---

### 🔹 High-Risk Transaction Rate
- **Definition:** Percentage of transactions flagged as risky  
- **Formula:** `risky_transactions / TOTAL TRANSACTIONS`  
- **Why it matters:**  
  Provides an **early warning signal** for emerging fraud patterns  

---

## 👤 3. User Behavior Metrics

These metrics help understand **how users interact with the platform** and identify abnormal patterns.

---

### 🔹 Transactions per User
- **Definition:** Average number of transactions per user  
- **Formula:** `TOTAL TRANSACTIONS / TOTAL USERS`  
- **Why it matters:**  
  Helps distinguish:
  - Power users  
  - Casual users  

---

### 🔹 Average Spend per User
- **Definition:** Average total spend per user  
- **Formula:** `TOTAL SUCCESS AMOUNT / TOTAL USERS`  
- **Why it matters:**  
  Identifies high-value users and revenue concentration  

---

### 🔹 Device Count per User
- **Definition:** Number of devices used per user  
- **Formula:** `COUNT(DISTINCT device_id per user)`  
- **Why it matters:**  
  Higher values may indicate:
  - Normal multi-device usage  
  - Suspicious behavior (account sharing, spoofing)  

---

### 🔹 Velocity Transactions
- **Definition:** Number of transactions within a short time window  
- **Why it matters:**  
  Detects abnormal rapid activity, often associated with fraud  

---

## 💳 4. Payment Performance Metrics

These metrics evaluate **how well different payment methods perform**.

---

### 🔹 Failure Rate by Payment Method
- **Definition:** Failure percentage for each payment method  
- **Why it matters:**  
  Identifies weak or unreliable payment channels  

---

### 🔹 Retry Rate
- **Definition:** Percentage of failed transactions followed by a retry  
- **Formula:** `retry_transactions / failed_transactions`  
- **Why it matters:**  
  Indicates user friction and persistence  

---

### 🔹 Success After Retry Rate
- **Definition:** Percentage of retries that result in success  
- **Why it matters:**  
  Helps determine whether failures are:
  - Temporary (system/network issues)  
  - Permanent (user/payment problems)  

---

## 🏪 5. Merchant Metrics

These metrics help evaluate **merchant performance and risk contribution**.

---

### 🔹 Revenue / GPV per Merchant
- **Definition:** Total transaction value processed by each merchant  
- **Why it matters:**  
  Identifies high-value merchants driving platform revenue  

---

### 🔹 Fraud Rate per Merchant
- **Definition:** Fraud percentage for each merchant  
- **Why it matters:**  
  Detects merchants associated with higher risk activity  

---

### 🔹 Refund Rate per Merchant
- **Definition:** Refund percentage per merchant  
- **Why it matters:**  
  Indicates:
  - Service quality issues  
  - Operational inefficiencies  

---

## 🎯 Important Interpretation Notes

- **SUCCESS** → Money successfully moved  
- **REFUNDED** → Money reversed after completion  
- **FRAUDULENT** → Risk signal (not always direct financial loss)  

Understanding these distinctions is critical when interpreting metrics like revenue, fraud exposure, and net value.

---

## 🔥 One-Line Summary

These metrics together provide a complete view of platform growth, payment reliability, financial movement, and risk exposure across users, merchants, and payment systems.
