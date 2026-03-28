# 💳 FlowPay — Payment Risk & Performance Analysis

## 🧠 About This Project

This project is an end-to-end analysis of a digital payments platform (FlowPay), focused on understanding:

- How the platform is performing overall  
- Where revenue is being lost  
- What kind of fraud risks exist  
- How user and merchant behavior impacts the system  

Instead of looking at isolated metrics, I approached this like a real-world analyst — breaking the problem into layers and moving from:

**what is happening → why it’s happening → what should be done**

---

## 🎯 Problem Statement

As FlowPay scales, a few issues start becoming more visible:

- Payment failures are relatively high  
- Fraud reports are increasing  
- Certain merchants show higher refunds  
- Some user behaviors look suspicious  

Individually, these may not seem critical. But at scale, even small inefficiencies can lead to:

- Significant revenue loss  
- Poor user experience  
- Increased operational overhead  

The goal of this project was to move from:

> “We see problems”  
to  
> “We understand where, why, and what to fix”

---

## 🔍 What I Did

I structured the analysis into multiple layers to keep things realistic and avoid mixing signals.

### 1. Platform Health
- Transaction volume and growth  
- Success, failure, and fraud rates  
- GPV and net revenue  

👉 Helped understand overall system stability

---

### 2. Payment Performance
- Failure rates by payment method  
- Device-level differences  
- City-level performance  
- High-value transaction behavior  

👉 Identified where payments are breaking

---

### 3. Merchant Analysis
- Revenue contribution  
- Fraud & refund rates  
- Category-level risk patterns  
- Outlier merchants  

👉 Showed that risk is concentrated, not uniform

---

### 4. User Behavior Analysis
- Transaction frequency  
- Retry behavior  
- Velocity patterns  
- Device and location usage  

👉 Helped identify behavioral signals of friction and risk

---

### 5. Revenue Loss Analysis
- Breakdown of loss (failure vs fraud vs refund)  
- Retry recovery efficiency  
- Segment-level loss patterns  

👉 This was the most important layer for business impact

---

### 6. Conversion Funnel
- Attempt → Success → Refund flow  
- Drop-off analysis  

👉 Connected user behavior to revenue outcomes

---

### 7. Fraud & Refund Type Analysis
- Fraud categories (account takeover, identity theft, etc.)  
- Refund reasons (wrong amount, duplicate, merchant issues)  

👉 Added real-world meaning behind the numbers

---

### 8. Risk Scoring Model
- Built a simple behavior-based segmentation  
- Classified users into low, medium, and high risk  

👉 Simulates how real fintech systems make decisions

---

## 💡 Key Insights

### 🔴 1. Failures are the biggest problem (not fraud)

- ~70% of revenue loss comes from failed transactions  
- Fraud and refunds are smaller contributors  

👉 This was unexpected and became the main focus

---

### 🔁 2. Retry works… but not enough

- Retry success rate is high  
- But only ~25% of failed transaction value is recovered  

👉 High-value transactions are still being lost

---

### 💳 3. Payment system is stable, but not optimized

- ~88% success rate  
- ~1 in 10 transactions still fail  

👉 At scale, this is a major revenue opportunity

---

### 🏪 4. Risk is concentrated, not widespread

- Small group of merchants drive:
  - High fraud  
  - High refunds  

👉 This is a targeted risk problem, not a platform-wide issue

---

### 👤 5. User behavior is mostly healthy

- No heavy dependence on power users  
- High-value users are more reliable  

👉 Strong sign for scalability

---

### ⚡ 6. Behavioral signals matter more than static ones

- Strong signals:
  - Velocity  
  - Retry behavior  

- Weak signals:
  - Device count  
  - Location changes  

👉 Fraud detection requires combining signals

---

### 🔐 7. Fraud is identity-driven

- Account takeover & identity theft dominate  
- Not just payment-level fraud  

👉 Focus should be on behavioral + access control

---

### 🔁 8. Refunds are operational, not behavioral

- Top reasons:
  - Wrong amount  
  - Duplicate transactions  
  - Merchant errors  

👉 Refunds are mostly system/merchant issues

---

## 💰 Business Impact

- Total revenue leakage: **~₹810M**  
- Major loss driver: **Failures (~70%)**

### 💣 Potential Recovery

By improving:

- Payment success rate  
- Retry recovery  
- High-value transaction handling  

👉 Estimated recoverable value:

**₹275M – ₹350M+**

---

## 🚀 What I Would Do

### 1. Improve payment success rate
- Optimize gateway performance  
- Reduce card failures  

---

### 2. Optimize retry strategy
- Smarter retry timing  
- Focus on high-value transactions  

---

### 3. Apply risk-based controls
- Strict checks for high-risk users  
- Seamless experience for low-risk users  

---

### 4. Monitor high-risk merchants
- Especially gaming & real estate categories  

---

### 5. Reduce refunds
- Fix duplicate and incorrect transactions  
- Improve merchant processes  

---

## ⚠️ Dataset Notes

- The dataset used in this project was **AI-generated using Tonic.ai**  
- It was designed to simulate a real fintech transaction environment  

However:

- Some variables show **uniform distribution (especially merchant activity)**  
- Retry success rates are **higher than real-world scenarios**  
- Fraud signal separation is **weaker than production datasets**

👉 Because of this:

**Insights should be interpreted directionally rather than as exact real-world benchmarks**

That said, the dataset still allowed meaningful analysis of:

- System inefficiencies  
- Behavioral patterns  
- Risk segmentation approaches  

---

## 🧠 What I Learned

This project changed how I think about analytics:

- Not all problems are equally important  
- The biggest issue is often not the most obvious one  
- Good analysis is about prioritization, not just insights  

Most importantly:

> Improving existing systems can be more valuable than acquiring new users

---

## 🔥 Final Takeaway

FlowPay is a strong and scalable platform, but it is losing a significant amount of revenue due to payment failures and inefficient recovery.

By focusing on:

- Payment reliability  
- High-value transaction recovery  
- Targeted risk controls  

the platform can unlock high-impact improvements without increasing acquisition costs.

---

## 👤 About Me

I’m an aspiring Data Analyst focused on:

- SQL-based analysis  
- Business problem solving  
- Turning data into actionable insights  

This project is part of my effort to build **real-world, decision-focused analytics skills**.

---

## ⭐ If You’re a Recruiter

I’d love to hear your feedback or discuss this project further.
