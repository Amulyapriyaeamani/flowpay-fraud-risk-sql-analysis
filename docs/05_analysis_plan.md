# 🧠 FlowPay — Analysis Plan

## Fraud & Payment Risk Investigation

In this project, I approached the problem the same way an analytics team in a fintech company would.

Instead of jumping straight into queries, I structured the analysis to answer real business questions step by step — focusing on **platform performance**, **operational inefficiencies**, and **risk patterns across users, merchants, and transactions**.

The end goal is not just insights, but building a **behavior-based risk scoring model** that can actually be used for decision-making.

---

## 🔍 Investigation Approach

To keep the analysis structured and practical, I followed a layered approach:

1. Understand overall platform performance and revenue flow  
2. Identify operational weaknesses in the payment system  
3. Analyze payment method performance and failure patterns  
4. Evaluate merchant-level risk and operational issues  
5. Detect behavioral signals from user activity  
6. Segment users based on activity and value  
7. Quantify revenue leakage (failures, fraud, refunds)  
8. Build a behavior-based risk scoring model  

This mirrors how **product, risk, and analytics teams typically work together** — starting broad and gradually drilling down into specific problem areas.

---

## ⚙️ SQL Techniques Used

To simulate real-world analytics workflows, I used:

- Multi-table joins across transactions, users, and merchants  
- Common Table Expressions (CTEs) to break down complex logic  
- Window functions to analyze user behavior patterns  
- Aggregations for business-level insights  
- Conditional logic to create fraud and risk signals  

The focus was not just writing queries, but writing them in a way that reflects **production-level analytical thinking**.

---

## 📊 1. Platform Overview

### What I checked

- Total transactions and revenue (GPV)  
- Success, failure, fraud, and refund rates  
- Average transaction value  

### Why this matters

Before going deep, I needed a clear baseline of how the platform is performing overall.

### Business impact

Gives a quick snapshot of platform health and highlights whether there are any obvious red flags.

---

## 💳 2. Payment Performance Analysis

### What I checked

- Transaction volume by payment method  
- Success and failure rates by method  
- Failure rates by device type  
- Failure rates by city  
- Performance of high-value transactions  

### Why this matters

Different payment methods often behave very differently — this helps identify weak points in the system.

### Business impact

Insights from this section can directly improve **payment success rates and user experience**.

---

## 🏪 3. Merchant Risk & Performance Analysis

### What I checked

- Fraud rate by merchant  
- Refund rate by merchant  
- Fraud trends by merchant category  
- High-risk merchant segments  
- Revenue distribution across merchants  

### Why this matters

A small group of merchants often contributes disproportionately to risk.

### Business impact

Helps in **targeted monitoring, stricter controls, or intervention at the merchant level**.

---

## 👤 4. User Behavior Analysis

### What I checked

- Transaction frequency per user  
- Spending patterns  
- Device usage behavior  
- Multi-city activity  
- High-velocity transactions (rapid activity)  
- Retry behavior after failures  

### Why this matters

Fraud is often behavioral — not just transactional.

### Business impact

This forms the foundation for **detecting suspicious activity early**.

---

## 🧩 5. User Segmentation

### What I checked

- High vs low activity users  
- High vs low spend users  
- Combined segments (activity + value)  

### Why this matters

Not all users should be treated the same.

### Business impact

Supports **personalized strategies for growth, retention, and risk control**.

---

## 💸 6. Revenue Loss Analysis

### What I checked

- Revenue lost due to failed transactions  
- Revenue lost due to fraud  
- Revenue reversed via refunds  
- Effectiveness of retries in recovering failed payments  

### Why this matters

Understanding *where money is leaking* is critical.

### Business impact

Helps prioritize **high-impact fixes that directly improve revenue retention**.

---

## 🔄 7. Conversion Funnel Analysis

### What I checked

- Success rate (conversion efficiency)  
- Failure vs fraud comparison  
- Refund rate after successful transactions  
- End-to-end revenue retention  

### Why this matters

This shows where users drop off in the payment lifecycle.

### Business impact

Identifies the **biggest bottlenecks affecting conversion and revenue**.

---

## 🔍 8. Fraud & Refund Pattern Analysis

### What I checked

- Fraud distribution by type  
- Refund distribution by reason  
- Overlap between fraud and refund signals  

### Why this matters

Not all refunds are fraud — and not all fraud shows up clearly.

### Business impact

Helps separate **true fraud signals from operational issues**, improving decision accuracy.

---

## ⚖️ 9. Risk Scoring Model (Behavior-Based)

### Signals I used

- Fraud history  
- Failure rate  
- Transaction velocity  
- Retry behavior  
- Number of devices used  
- Suspicious city activity  
- User segment (activity + value)  

### Output

Each user is classified into:

- 🟢 Low Risk  
- 🟡 Medium Risk  
- 🚨 High Risk  

### Why this matters

This step converts analysis into something actionable.

### Business impact

Enables:

- Targeted fraud prevention  
- Reduced false positives  
- Better user experience (less unnecessary friction)  

---

## 🎯 Final Outcome

By the end of this analysis, I was able to:

- Build a complete view of platform performance  
- Identify high-risk users and merchants  
- Detect behavioral fraud signals  
- Highlight payment inefficiencies  
- Quantify revenue leakage  
- Develop a practical risk scoring framework  

---

## 🔥 One-Line Summary

This project turns raw transaction data into a structured understanding of performance and risk — helping FlowPay move from reactive problem-solving to proactive, data-driven decisions.
