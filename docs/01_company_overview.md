# FlowPay — Company Overview

## 1. Platform Overview

FlowPay is a simulated **digital payments fintech platform** that enables users to send and receive money seamlessly through multiple payment methods such as UPI, wallet balance, and card payments.

The platform connects three core components of the payments ecosystem:

Users → Merchants → Payment Infrastructure

FlowPay allows users to:

* Send money using UPI
* Pay online merchants
* Scan QR codes at physical stores
* Use wallet balance
* Pay using credit and debit cards
* Perform peer-to-peer transfers

As the platform grows, transaction volume increases significantly, which introduces operational and risk management challenges such as:

* Transaction failures
* Fraudulent activities
* Merchant risk exposure
* Payment system performance issues

This project simulates the work of a **Product & Risk Analyst** analyzing the platform’s transaction data.

---

## 2. How Payments Work on FlowPay

A typical payment on FlowPay involves multiple components working together.

Step 1 — User Initiates Payment
A user selects a merchant or recipient and initiates a payment through the app.

Step 2 — Payment Method Selection
The user chooses a payment method:

* UPI
* Wallet
* Credit Card
* Debit Card

Step 3 — Payment Processing
The platform sends the payment request through payment infrastructure such as:

* Banks
* Payment gateways
* Card networks

Step 4 — Transaction Outcome
The transaction is then marked as one of the following:

* Success
* Failed
* Refunded
* Fraudulent

Each payment attempt is recorded as a **transaction event** in the system.

---

## 3. Transaction Lifecycle

Every payment in FlowPay follows a lifecycle from initiation to completion.

Initiated → Processing → Completed / Failed / Flagged

Possible outcomes include:

Successful Transaction
The payment is completed and funds are transferred to the merchant.

Failed Transaction
The payment fails due to reasons such as:

* Bank decline
* Network failure
* Insufficient balance
* Authentication issues

Refunded Transaction
The payment is reversed after completion due to:

* Customer disputes
* Duplicate payments
* Merchant cancellations

Fraudulent Transaction
Transactions identified as suspicious or fraudulent by the risk system or investigation team.

Understanding this lifecycle helps analysts monitor **platform health and payment reliability**.

---

## 4. Merchant Ecosystem

Merchants represent businesses that receive payments through FlowPay.

Merchant categories include:

* Food delivery
* E-commerce
* Gaming
* Utilities
* Travel
* Subscriptions
* Retail
* Bill payments

Different merchant categories behave differently in terms of:

* Transaction volume
* Success rates
* Fraud risk
* Refund rates

For example:
Gaming and digital goods merchants often show **higher fraud probability**, while utilities tend to have **higher success rates and lower risk**.

Monitoring merchant behavior is important for:

* Detecting suspicious merchants
* Managing risk exposure
* Improving payment success rates

---

## 5. Fraud Risk in Digital Payments

As digital payments scale, fraud becomes a major operational challenge for fintech platforms.

Common fraud patterns observed in payment systems include:

New Account Fraud
Fraudsters create new accounts and attempt high-value transactions immediately after signup.

Velocity Fraud
Multiple transactions attempted within a short time window (e.g., several payments within minutes).

Device Switching Fraud
Fraudsters frequently switch devices or use previously unseen devices.

High-Value Fraud
Unusual large transactions that deviate significantly from normal user behavior.

Location-Based Anomalies
Transactions initiated from locations different from the user’s registered city.

The objective of this project is to analyze FlowPay’s data to identify:

* Fraud patterns
* High-risk users
* Risky merchant categories
* Suspicious transaction behavior

These insights help the company improve fraud detection systems and reduce financial losses.
