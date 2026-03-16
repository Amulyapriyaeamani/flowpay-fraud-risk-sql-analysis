# Platform Health Overview

## Objective

The first step in the investigation is to understand the overall health and performance of the FlowPay platform.  
This includes analyzing transaction volume, revenue processed, user activity, and the distribution of transaction outcomes.

The goal is to establish a baseline understanding of platform performance before moving into deeper analysis such as payment performance, merchant risk, user behavior, and fraud detection.

---

# Key Platform Metrics

## Total Transactions

**Value:** 999,996

This represents the total number of payment attempts recorded in the dataset during the analysis period.

This metric helps measure the overall scale of platform activity.

---

## Revenue Processed

**Value:** ₹3.35 Billion

**Calculation:**

(SUCCESS + REFUNDED)

Revenue processed represents the total payment value that successfully passed through the platform's payment infrastructure.

Refunded transactions are included because the payment was initially processed successfully before being reversed.

This metric is similar to **Gross Payment Volume (GPV)** used by payment companies such as :contentReference[oaicite:0]{index=0} and :contentReference[oaicite:1]{index=1}.

---

## Monthly Transaction Volume

**Value:** ~83,333 transactions per month

Transaction activity appears evenly distributed across the twelve months of the dataset.

This uniform distribution indicates that the dataset was synthetically generated to maintain balanced activity throughout the year rather than reflecting real seasonal patterns.

In real-world platforms, transaction volume typically varies due to holidays, promotions, and seasonal behavior.

---

## Active Users

**Value:** 23,452 users

Out of the 25,000 registered users, approximately 23,452 users performed at least one transaction.

This suggests that roughly **94% of registered users are active**, indicating strong user engagement on the platform.

---

## Average Transaction Value (ATV)

**Value:** ₹3,783.80

**Calculation:**

(SUCCESS + REFUNDED)

Average Transaction Value represents the average size of completed payments processed by the platform.

Failed transactions are excluded because no payment was processed in those cases.

---

# Transaction Outcome Metrics

Transaction outcomes are categorized into four types:

- SUCCESS
- FAILED
- REFUNDED
- FRAUDULENT

Each outcome represents a different operational or risk-related event on the platform.

---

## Success Rate

**Value:** 85.58%

**Calculation:**

SUCCESS / TOTAL TRANSACTIONS

This metric measures the proportion of transactions that completed successfully and resulted in a finalized purchase.

A high success rate generally indicates stable payment processing infrastructure and reliable transaction execution.

---

## Failure Rate

**Value:** 9.68%

**Calculation:**

FAILED / TOTAL TRANSACTIONS

The failure rate represents the proportion of payment attempts that did not complete successfully.

Failures may occur due to reasons such as bank declines, insufficient funds, payment gateway issues, or connectivity problems.

Further investigation will analyze how failure rates vary across payment methods, devices, and geographic locations.

---

## Refund Rate

**Value:** 3.38%

**Calculation:**

REFUNDED / (SUCCESS + REFUNDED)

Refund rate measures the percentage of completed payments that were later reversed.

Refunds may occur due to product returns, service cancellations, customer disputes, or merchant processing errors.

This metric helps evaluate post-payment transaction stability and merchant quality.

---

## Fraud Rate

**Value:** ~1.75%

**Calculation:**

FRAUDULENT / TOTAL TRANSACTIONS

Fraudulent transactions represent payments that were later identified as suspicious or malicious activity.

Although the fraud rate is relatively low compared to total platform activity, identifying patterns in fraudulent transactions is critical for improving risk monitoring and fraud prevention systems.

---

# Summary

The platform processed approximately **1 million transactions**, handling over **₹3.35 billion in payment volume** during the analysis period.

Key observations include:

- High transaction success rate (~86%)
- Moderate failure rate (~10%)
- Low refund rate (~3%)
- Fraud activity representing a small but significant portion of transactions (~1.75%)
- Strong user engagement with most registered users actively transacting

Overall, the platform appears operationally stable.  
However, the failure and fraud rates indicate areas that require deeper investigation in the subsequent stages of analysis.

The next phase focuses on **Payment Performance Analysis**, which investigates the causes of transaction failures and operational inefficiencies within the payment system.
