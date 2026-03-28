# Risk Scoring Model — Final Insights

This section evaluates how well the risk scoring model performs, what it reveals about user behavior, and how it can be applied in real business decisions.

---

## 1. Model Validation

### Risk Segmentation Performance

| Risk Level | Fraud Rate | Failure Rate |
|-----------|-----------|-------------|
| High Risk   | 4.09%  | 14.62% |
| Medium Risk | 3.72%  | 8.15%  |
| Low Risk    | 0.00%  | 8.93%  |

### Interpretation

#### Strong Separation in Fraud

- High Risk → 4.09%  
- Low Risk → 0%  

There is a clear and meaningful separation between safe and risky users.

#### Failure Behavior

- High-risk users show the highest failure rates (~14.6%)  
- Medium and low-risk users are relatively similar (~8–9%)  

**Key Insight**

The model effectively differentiates user risk, with high-risk users showing significantly higher fraud rates while low-risk users remain clean.

---

## 2. Revenue Distribution (Critical Insight)

### Revenue by Risk Segment

| Risk Level | Revenue |
|-----------|--------|
| High Risk   | ₹825M |
| Medium Risk | ₹2.62B |
| Low Risk    | ₹1.50B |

### Interpretation

#### Medium Risk Drives the Business

- ~₹2.62B (~53% of total revenue)  
- Represents the largest and most important user segment  

#### High Risk Still Matters

- ~₹825M (~17% of revenue)  

These users are risky, but they also contribute meaningful revenue.

#### Low Risk is the Safest Segment

- ~₹1.50B (~30%)  
- No observed fraud  
- Stable and predictable behavior  

**Combined Insight**

High-risk users contribute a smaller share of revenue but carry the highest fraud and failure rates. This creates a clear trade-off between controlling risk and protecting revenue, requiring targeted rather than blanket actions.

---

## 3. Validation Using Fraud Reports

### Fraud Detection Performance

| Risk Level | Fraud Users | Total Users | Fraud Rate |
|-----------|------------|------------|-----------|
| High Risk   | 2466 | 3573  | 69.02% |
| Medium Risk | 7173 | 11060 | 64.86% |
| Low Risk    | 0    | 10367 | 0%     |

### What Works Well

#### Low Risk Segment is Highly Reliable

- Zero fraud users  
- 0% fraud rate  

**Insight**

The model is extremely effective at identifying safe users.

---

### What Needs Improvement

#### Weak Separation Between Medium and High Risk

- High Risk → 69%  
- Medium Risk → 65%  

The difference is relatively small.

### Possible Reasons

- Dataset characteristics (AI-generated data may have higher fraud density)  
- Overlap in behavioral signals (e.g., retries, velocity, failures)

**Key Insight**

The model clearly separates safe users from risky users, but struggles to distinguish between medium and high-risk segments.

---

## 4. False Positives and Trade-Off

### Clean Users by Segment

| Segment     | Clean Users |
|------------|------------|
| High Risk   | 1107 |
| Medium Risk | 3887 |
| Low Risk    | 10367 |

### Insight

The model captures most fraudulent users but also flags a portion of genuine users as high risk.

### Business Implication

- Strict blocking reduces fraud  
- But also impacts genuine users and revenue  

**Recommended Approach**

- Step-up authentication (OTP, KYC)  
- Manual review for high-risk cases  
- Transaction limits instead of outright blocking  

---

## 5. Key Observation: Failures are System-Driven

- Low Risk Failure Rate (~8.93%) ≈ Medium Risk (~8.15%)

**Insight**

Failure rates remain consistent across segments, indicating that failures are more likely driven by system or infrastructure issues rather than user behavior.

---

## 6. Business Strategy by Segment

### High-Risk Users

- High fraud and high failure rates  
- Still contribute meaningful revenue  

**Approach**

- Apply step-up authentication  
- Limit high-value transactions  
- Monitor aggressively  

Avoid blanket blocking.

---

### Medium-Risk Users (Most Important Segment)

- Largest share of revenue  
- Moderate risk profile  

**Approach**

- Apply friction selectively  
- Trigger checks dynamically  
- Focus on improving success rates  

---

### Low-Risk Users

- No fraud observed  
- Stable behavior  

**Approach**

- Minimize friction  
- Enable fast and seamless checkout  
- Maximize conversion  

---

## 7. Business Impact

### Without Risk Segmentation

- Same rules applied to all users  
- Inefficient balance between fraud control and conversion  

### With Risk Model

- Reduced fraud exposure  
- Improved success rates  
- Higher revenue recovery  
- Reduced unnecessary friction  
- Better overall user experience  

---

## Final Insight

The risk scoring model enables a shift from a one-size-fits-all system to a differentiated approach.

Low-risk users can experience seamless transactions, while high-risk users are subject to stricter controls. This balance improves both revenue retention and fraud prevention.

---

## Interview Summary

The model effectively segments users into low, medium, and high risk. High-risk users show significantly higher fraud (~4%) and failure (~14.6%) rates, while low-risk users remain clean.

However, high-risk users still contribute meaningful revenue, highlighting the need for targeted controls rather than blanket restrictions. Additionally, similar failure rates across segments indicate that system inefficiencies, not user behavior, are the primary driver of transaction failures.

This suggests that the highest business impact comes from improving payment success rates while applying risk-based controls selectively.
