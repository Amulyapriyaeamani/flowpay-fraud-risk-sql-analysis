# 🏪 Merchant Risk & Performance Analysis

This section evaluates merchant performance across **revenue contribution, transaction behavior, fraud risk, and operational issues**.

The goal is to answer:

> **Which merchants drive the business, and which merchants introduce risk?**

---

# 📊 1. Platform Context (Baseline)

- **Total Payment Attempts:** ~972K  
- **Total GPV:** ~₹4.9 Billion  
- **Average Transaction Value (ATV):** ~₹5,765  
- **Fraud Rate:** ~2.38%  
- **Refund Rate:** ~2.89%  

These benchmarks act as **reference points** to evaluate merchant-level deviations.

---

# 💰 2. Revenue Contribution & Concentration

### 🔝 Top Merchants by Revenue

Top merchants include:

- Fuel & Utilities → BPCL, Shell, Airtel, BSNL  
- Gaming → MPL, Dream11, A23  
- EdTech → Simplilearn, Great Learning  
- Commerce & Services → Jio Store, PolicyBazaar  

### 📊 Key Observation

- **Top 20 merchants contribute ~₹120M (~12 Cr)**  
- Compared to total GPV (~₹4.9B), contribution is **very low (~2.4%)**

---

### 🧠 Insight

- Revenue is **highly distributed across merchants**
- No single merchant or small group dominates the platform  

👉 This indicates:

- **Low dependency risk**
- Strong **ecosystem diversification**
- High scalability without concentration bottlenecks  

---

# 🔄 3. Transaction Volume Distribution

- **Max transactions per merchant:** ~1084  
- **Min transactions:** ~873  
- **Average:** ~973  

---

### 🧠 Insight

Transaction volume is **extremely uniform across merchants**

👉 This suggests:

- Balanced merchant activity  
- No hyper-dominant or inactive merchants  
- Stable and evenly utilized ecosystem

- The dataset shows unusually uniform transaction distribution across merchants, which is not typical in real-world platforms. This suggests the data is simulated, but it still allows us to analyze relative performance and risk patterns.

---

# 💳 4. Average Transaction Value (ATV)

- **Max ATV:** ~₹7,339  
- **Min ATV:** ~₹4,150  
- **Platform Avg:** ~₹5,765  

---

### 🧠 Insight

ATV variation aligns with **business models**:

- Higher ATV → EdTech, Fuel  
- Lower ATV → Gaming, Retail  

👉 No extreme spikes detected

---

### ✅ Conclusion

- Pricing behavior is **consistent and category-driven**
- No strong evidence of **value manipulation or pricing anomalies**

---

# 🚨 5. Fraud Risk Analysis

## 🔥 Fraud Rate Distribution

- **Platform Avg:** ~2.38%  
- **Highest:** ~6.75%  
- **Lowest:** ~0.81%  
- **Merchants above avg fraud:** **411 / 1000 (~41%)**

---

### 🧠 Insight

- Fraud is **not rare** — a significant portion of merchants exceed average  
- However, severity varies widely → indicates **uneven risk distribution**

---

## 🚨 High Fraud Merchants (Critical)

Examples:

- WinZO (6.75%) — Gaming  
- Samsung Store (6.65%) — Electronics  
- Apollo Pharmacy (6.18%) — Healthcare  
- LG Shoppe (5.58%) — Electronics  
- Square Yards (5.49%) — Real Estate  

---

### 🧠 Insight

These merchants show **2–3x higher fraud than platform average**

👉 Indicates:

- Fraud is **merchant/category driven**, not random  
- Certain merchants act as **risk hotspots**

---

# 💰 6. Fraud Exposure (Financial Impact)

Top merchants by fraud value:

- Via Travel (~₹6.8L)  
- Wonderla (~₹5.4L)  
- Malabar Gold (~₹4.8L)  
- Box8 (~₹4.5L)  
- DMart (~₹4.4L)  

---

### 🧠 Insight

- Fraud impact is **concentrated in a few merchants**
- Not all high fraud-rate merchants have high monetary impact  

👉 Important distinction:

> **High fraud rate ≠ High financial loss**

---

# 📊 7. Fraud by Merchant Category

| Category        | Fraud Rate |
|---------------|-----------|
| Gaming        | 2.84% 🔴 |
| Real Estate   | 2.80% 🔴 |
| Jewelry       | 2.63% |
| Electronics   | 2.49% |
| Entertainment | 2.42% |
| Travel        | 2.39% |
| Fuel          | 2.16% 🟢 |

---

### 🧠 Insight

- Gaming & Real Estate → **highest fraud-prone categories**
- Utilities, Fuel → **lowest risk**

---

### 🔥 Key Business Insight

> Fraud risk is **strongly category-dependent**

👉 Enables:
- Category-level monitoring  
- Risk-based merchant controls  

---

# 🚨 8. High-Risk Merchant Segment

- **71 merchants** identified with:
  - Above-average fraud  
  - High transaction volume  

---

### 🧠 Insight

These are **statistically significant risk contributors**

Examples:
- 99acres  
- FreshMenu  
- WinZO  
- GoIbibo  
- BookMyShow  

---

👉 These merchants require:
- Continuous monitoring  
- Risk controls  
- Possibly stricter validation  

---

# 🔁 9. Refund Analysis

- **Max refund rate:** ~8.65%  
- **Min:** ~0.92%  
- **Platform Avg:** ~2.89%  

### Top Refund Merchants:

- Westside (8.65%)  
- MagicBricks (8.01%)  
- Square Yards (7.97%)  
- WinZO (7.88%)  

---

### 🧠 Insight

- Some merchants show **2–3x higher refund rates**
- Indicates:

👉 Possible issues:
- Customer dissatisfaction  
- Order cancellations  
- Operational inefficiencies  

---

# ⚖️ 10. Risk Segmentation (Decision Layer)

| Segment | Merchants | GPV Contribution |
|--------|----------|----------------|
| Normal | 875 | ₹4.28B |
| High Refund + High Revenue | 102 | ₹542M |
| High Fraud + High Volume | 23 | ₹120M |

---

### 🧠 Insight

- Majority of platform is **healthy (875 merchants)**  
- Small segments contribute **disproportionate risk**

---

### 🚨 Critical Insight

> A very small group of merchants contributes to a large portion of risk

---

# 🔍 11. Outlier Detection

## 🚨 Extremely High Fraud vs Category

Examples:

- WinZO (6.75% vs 2.84%)  
- Samsung Store (6.65% vs 2.49%)  
- Apollo Pharmacy (6.18% vs 2.22%)  

---

### 🧠 Insight

These merchants are:

- **Statistical outliers**
- Not just high — **abnormally high vs peers**

👉 Strong fraud indicators

---

## 💳 Very High ATV vs Category

Examples:

- Simplilearn (+₹1500 vs category avg)  
- BPCL (+₹1396)  
- Dream11 (+₹1291)  

---

### 🧠 Insight

- Some merchants operate at **significantly higher ticket sizes**
- Could indicate:
  - Premium pricing  
  - OR potential high-value fraud risk  

---

## ⚠️ High Failure + High Fraud (Danger Zone)

Examples:

- WinZO  
- Samsung Store  
- Apollo Pharmacy  
- LG Shoppe  

---

### 🧠 Insight

> These merchants fail AND commit fraud at higher rates

👉 Strong signal of:
- System abuse  
- Risky transaction behavior  

---

# 🔥 Final Conclusion

The merchant ecosystem is **well-balanced and scalable**, with:

- Even distribution of transactions  
- No heavy dependency on individual merchants  

However:

- Fraud and refund risks are **highly concentrated**
- Certain merchants and categories act as **risk hotspots**

---

### 🎯 Key Takeaway

> The platform does not have a scale problem — it has a **targeted risk problem**

---

### 🚀 What This Enables

- Focused risk mitigation (not platform-wide restrictions)  
- Merchant-level monitoring  
- Category-based fraud controls  

---
