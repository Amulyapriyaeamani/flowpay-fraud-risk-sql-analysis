# 💳 FlowPay — Payment Method Analysis

This section evaluates **payment performance across different methods, devices, and locations**.

The goal is to answer:

> **Which payment methods perform best? Where are failures happening?**

---

# 📊 1. Transaction Volume by Payment Method

| Payment Method | Transaction Volume |
|----------------|-------------------|
| UPI            | 526,871           |
| Wallet         | 192,950           |
| Credit Card    | 152,703           |
| Debit Card     | 100,386           |

**Insight:**

- **UPI dominates** the platform (~50%+ share)
- Cards are secondary, wallets sit in the middle
- Platform heavily dependent on UPI ecosystem

---

# ⚙️ 2. Success Rate by Payment Method

| Payment Method | Success Rate (%) |
|----------------|------------------|
| UPI            | 88.54            |
| Wallet         | 88.30            |
| Debit Card     | 87.56            |
| Credit Card    | 87.54            |

**Insight:**

- All methods perform **consistently (~87–88%)**
- **UPI slightly leads**, making it both high-volume and high-performing
- No major reliability gaps across methods

---

# ❌ 3. Failure Rate by Payment Method

| Payment Method | Failure Rate (%) |
|----------------|------------------|
| Debit Card     | 10.55            |
| Credit Card    | 10.45            |
| Wallet         | 9.31             |
| UPI            | 8.90             |

**Insight:**

- **Cards have highest failure rates**
- **UPI is most reliable**
- Likely causes:
  - Bank declines
  - OTP/authentication issues for cards

---

# 💰 4. Revenue Contribution (GPV)

| Payment Method | GPV |
|----------------|----------------------|
| UPI            | 2,355,642,554.01     |
| Credit Card    | 1,098,912,921.43     |
| Wallet         | 871,507,144.71       |
| Debit Card     | 622,797,840.94       |

**Insight:**

- **UPI drives the majority of revenue**
- Credit Cards contribute high value despite lower volume
- Debit Cards underperform both in volume and value

---

# 💸 5. Average Transaction Value (ATV)

| Payment Method | Avg Transaction Value |
|----------------|----------------------|
| Credit Card    | 8,221.09             |
| Debit Card     | 7,085.38             |
| Wallet         | 5,115.17             |
| UPI            | 5,049.92             |

**Insight:**

- **Cards = high-value transactions**
- **UPI & Wallet = low-to-mid value transactions**
- Clear segmentation:
  - Cards → big purchases  
  - UPI → everyday payments  

---

# 📱 6. Failure Rate by Device Type

| Device Type | Failure Rate (%) |
|-------------|------------------|
| iOS         | 9.79             |
| Android     | 9.22             |

**Insight:**

- Slightly higher failures on **iOS**
- Could indicate:
  - App optimization issues  
  - Payment integration differences  

---

# 🌍 7. Failure Rate by City (Top Highlights)

| City | Failure Rate (%) |
|------|------------------|
| Delhi | 9.89 |
| Bhopal | 9.86 |
| Pune | 9.62 |
| Nagpur | 9.59 |
| Indore | 9.57 |
| ... | ... |
| Thiruvananthapuram | 8.75 |

**Insight:**

- Failure rates are **fairly consistent (~8.7% – 9.9%)**
- Slightly higher in **metro & high-traffic cities**
- No extreme outliers → system is geographically stable

---

# 🔍 8. Transaction Outcomes by Payment Method

| Method | Success | Failure | Fraud | Refund |
|--------|--------|--------|-------|--------|
| UPI | 466,471 | 46,873 | 13,527 | 14,961 |
| Wallet | 170,377 | 17,954 | 4,619 | 5,103 |
| Credit Card | 133,670 | 15,951 | 3,082 | 3,390 |
| Debit Card | 87,899 | 10,588 | 1,899 | 2,159 |

**Insight:**

- UPI has:
  - Highest success  
  - Highest fraud & refunds (due to scale)  
- Fraud is proportional to usage, not abnormal in any one method  

---

# 💎 9. High-Value Transactions: Success vs Failure

| Transaction Type | Success | Failure | Fraud |
|------------------|--------|--------|-------|
| Regular          | 769,361 | 80,872 | 20,756 |
| High Value       | 89,056  | 10,494 | 2,371  |

**Insight:**

- High-value transactions:
  - Lower volume but significant failures  
- Indicates:
  - Stricter checks  
  - Higher friction (bank/security layers)

---

# 🎯 Key Takeaways

- **UPI = Backbone of the platform**
  - Highest volume, revenue, and success rate  

- **Cards = High-value but less reliable**
  - Higher failure rates  
  - Used for larger transactions  

- **Wallet = Balanced performer**
  - Moderate volume, stable performance  

- **Failures are consistent across regions**
  - No major geographic risk  

- **Fraud scales with usage**
  - No single payment method is disproportionately risky  

---

# 🔥 One-Line Summary

The platform is **UPI-driven, card-supported, and stable overall**, with **higher failures in card payments and high-value transactions** but no major structural weaknesses.
