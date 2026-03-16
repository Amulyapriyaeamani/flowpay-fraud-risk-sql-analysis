# Platform Health Overview

## Objective

The first step in the investigation is to understand the overall health and operational performance of the FlowPay platform.  
This involves analyzing transaction volume, payment throughput, user participation, and the distribution of transaction outcomes.

The goal of this stage is to establish a baseline understanding of the platform before investigating payment failures, merchant risk, user behavior patterns, and fraud signals in later phases of the analysis.

---

# Key Platform Metrics

## Total Transactions

**Value:** 999,996

This represents the total number of payment attempts recorded on the platform during the analysis period.

Each record corresponds to a transaction attempt made by a user to pay a merchant.  
This metric provides a baseline measure of overall platform activity and scale.

---

## Revenue Processed (Gross Payment Volume)

**Value:** ₹3.35 Billion

**Calculation**

(SUCCESS + REFUNDED)

Revenue processed represents the **total value of payments successfully processed by the platform's payment system**, regardless of whether the payment was later refunded.

Refunded transactions are included because the payment was initially completed before the refund was issued.

Fraudulent transactions are excluded from this metric because they represent payments identified as illegitimate and therefore do not represent valid economic activity on the platform.

This metric is similar to **Gross Payment Volume (GPV)** used by payment infrastructure companies such as Stripe or Razorpay to measure the total value of transactions handled by the platform.

---

## Monthly Transaction Volume

**Value:** ~83,333 transactions per month

Monthly transaction activity appears evenly distributed across all twelve months of the dataset.

In real-world payment platforms, transaction volumes usually fluctuate due to factors such as seasonal shopping patterns, marketing campaigns, and major holidays.

The uniform distribution observed here suggests that the dataset was synthetically generated with balanced monthly activity to simplify analysis and ensure consistent data coverage across the entire year.

---

## Active Users

**Value:** 23,452 users

Out of 25,000 registered users in the dataset, approximately 23,452 users performed at least one transaction during the analysis period.

This indicates that roughly **94% of registered users were active**, suggesting strong platform engagement and frequent user participation in transactions.

---

## Average Transaction Value (ATV)

**Value:** ₹3,783.80

**Calculation**

(SUCCESS + REFUNDED)

Average Transaction Value represents the average size of completed payments processed on the platform.

Failed transactions are excluded because they represent payment attempts that did not successfully process any monetary value.

This metric helps understand typical transaction size and overall spending behavior of users on the platform.

---

# Transaction Outcome Metrics

Transactions on the platform fall into four possible outcome categories:

- SUCCESS
- FAILED
- REFUNDED
- FRAUDULENT

Each outcome represents a different operational or risk-related event within the payment lifecycle.

Analyzing the distribution of these outcomes helps evaluate platform reliability, customer experience, and potential fraud risk.

---

## Success Rate

**Value:** 88.57%

**Calculation**

(SUCCESS + REFUNDED) / TOTAL TRANSACTIONS

The success rate measures the proportion of payment attempts that were successfully processed by the platform's payment system.

In this dataset, transactions marked as REFUNDED represent payments that were initially processed successfully but later reversed due to events such as order cancellations, product returns, or merchant adjustments. Since the transaction table stores the final transaction state, refunded transactions are included in the success rate calculation.

A high success rate generally indicates stable payment processing infrastructure and a smooth checkout experience for users.

---

## Failure Rate

**Value:** 9.68%

**Calculation**

FAILED / TOTAL TRANSACTIONS

The failure rate represents the proportion of payment attempts that did not complete successfully.

Transaction failures may occur due to reasons such as bank declines, insufficient account balance, incorrect authentication, payment gateway errors, or connectivity issues.

Investigating the causes of transaction failures will be a key focus in the next stage of the analysis.

---

## Refund Rate

**Value:** 3.38%

**Calculation**

REFUNDED / (SUCCESS + REFUNDED)

The refund rate measures the percentage of completed payments that were later reversed.

Refunds may occur due to product returns, order cancellations, service disputes, or merchant processing errors.

A moderate refund rate can indicate normal customer behavior, while unusually high refund rates may signal operational issues or problematic merchants.

---

## Fraud Rate

**Value:** ~1.75%

**Calculation**

FRAUDULENT / TOTAL TRANSACTIONS

Fraudulent transactions represent payments that were later identified as suspicious or malicious activity.

Although fraud represents a relatively small proportion of total platform activity, it remains an important area of investigation because fraudulent transactions can lead to financial losses and reputational risk for the platform.

---

# Summary of Findings

The platform processed nearly **1 million transactions**, handling over **₹3.35 billion in payment volume** during the analysis period.

Key observations from the platform health analysis include:

- Strong overall transaction success rate (~86%)
- Moderate transaction failure rate (~10%)
- Relatively low refund activity (~3%)
- Fraudulent transactions accounting for a small but meaningful share (~1.75%)
- High user engagement with most registered users actively transacting

Overall, the platform appears to operate with stable payment processing performance and high user participation. However, the observed failure and fraud rates highlight the need for deeper investigation into payment reliability, merchant behavior, and suspicious transaction patterns.

---

# Next Step

The next phase of the investigation focuses on **Payment Performance Analysis**, which aims to identify patterns and potential causes behind transaction failures across payment methods, devices, and geographic locations.
