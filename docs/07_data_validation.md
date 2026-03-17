## Data Validation

This phase was focused on something more important than just “cleaning data” — **building trust in the dataset before using it for business decisions**.

In a payments system, even small inconsistencies can lead to incorrect conclusions about **revenue, fraud, or platform performance**. So the core question guiding this step was:

> **“Can this data be trusted for decision-making?”**

### 🔗 Relationship Integrity — Foundation of Trust

All relationship checks returned **zero issues**, which confirms:

*   Every transaction is linked to a valid **user, merchant, and device**
    
*   Every fraud report maps to an existing transaction
    
*   Every refund corresponds to a valid transaction
    

Why this matters:

Most analysis depends heavily on joins. Even a small number of broken relationships can silently distort metrics like:

*   Revenue by merchant
    
*   Fraud rate by user
    
*   Device-level risk analysis
    

**Interpretation:**There are no structural breaks in the data model. Joins and aggregations can be safely used without risk of hidden data loss.

### 🔁 Duplicate Checks — Preventing Metric Inflation

No duplicates were found at both:

*   **Technical level** (primary keys)
    
*   **Business level** (same user, amount, timestamp patterns)
    

This is critical because duplicate records would directly inflate:

*   Revenue
    
*   Transaction counts
    
*   Success rates
    

The absence of business-level duplicates also suggests:

*   No accidental retry duplication
    
*   No ingestion or logging issues
    

**Interpretation:**All count-based and revenue-based metrics are free from duplication bias.

### 💰 Transaction Amount Validation — Sanity & Distribution

Key observations:

*   No negative values
    
*   No zero-value transactions
    
*   Transaction range: **₹10 to ~₹2,00,000**
    
*   Average transaction value: **~₹5,700**
    

What this indicates:

*   The system is not recording invalid or corrupted payments
    
*   There is a natural spread between low and high-value transactions
    

This is especially important because:

*   High-value transactions often carry **higher fraud risk**
    
*   Payment failures tend to increase at higher amounts
    

**Interpretation:**The dataset supports meaningful segmentation (e.g., low vs high value) without requiring additional cleaning.

### 📱 Device Data Validation — Behavioral Signal Readiness

Key checks:

*   No missing device\_id in transactions
    
*   No device linked to multiple users
    
*   ~2,476 users are associated with multiple devices
    

The first two confirm **clean device tracking**, which is critical for fraud detection.

The third observation introduces an important behavioral pattern:

*   Could be normal (users switching devices)
    
*   Could indicate risk (account sharing, device spoofing)
    

**Interpretation:**Device data is structurally clean and rich enough to support meaningful behavioral and fraud analysis.

### 🚨 Fraud Consistency — Critical Business Signal

Two key findings:

*   No fraud reports exist for non-fraud transactions→ Reporting logic is consistent
    
*   ~9,668 fraudulent transactions have **no corresponding fraud report**
    

This is the most important observation in the validation phase.

From a data perspective, this is not an error.From a business perspective, this is a **potential risk signal**.

Possible reasons:

*   Fraud detection thresholds may be too high
    
*   Low-value fraud may be ignored
    
*   Manual review capacity may be limited
    
*   Reporting pipelines may have delays or filters
    

**Next-step analysis (analyst thinking):**

*   Compare reported vs unreported fraud by transaction amount
    
*   Check concentration across:
    
    *   Merchants
        
    *   Devices
        
    *   User segments
        
*   Evaluate detection and reporting thresholds
    

**Interpretation:**The dataset is valid, but highlights a **real business problem** — incomplete fraud reporting.

### 🔁 Refund Consistency — Financial Integrity

All refund-related checks passed:

*   Refunds only exist for valid transactions
    
*   No refunds for failed transactions
    
*   No over-refunds
    
*   No duplicate refunds
    

This confirms that:

*   Refund lifecycle is properly tracked
    
*   Revenue reversal logic is accurate
    

**Interpretation:**Financial metrics such as **net revenue and refund rate** can be trusted.

### 📊 Fraud Rate Sanity Check

*   Fraud rate observed: **~2.32%**
    

This falls within a realistic range:

*   Too high → possible data corruption
    
*   Too low → missing fraud records
    

**Interpretation:**Fraud exists at a meaningful and analyzable level without skewing results.

### ⏳ Temporal Consistency — Logical Flow

*   No transactions occur before user signup
    

This is essential because violations would break:

*   User lifecycle analysis
    
*   Cohort analysis
    
*   Behavioral timelines
    

**Interpretation:**Time-based and lifecycle analyses can be performed reliably.

### 🧠 Final Assessment — Is the Data Ready?

Yes — the dataset is **ready for analysis**.

Because:

*   Structural relationships are intact
    
*   No duplicates or invalid values
    
*   Financial flows are consistent
    
*   Behavioral signals are present and usable
    

### ⚠️ Not Perfect — And That’s Valuable

The presence of:

*   Unreported fraud
    
*   Multi-device users
    

are not data issues — they are **business signals**.

These patterns create opportunities for deeper analysis rather than requiring correction.

### 🎯 Analyst Mindset Going Forward

Data validation is not about proving that everything is perfect.

It’s about reaching a point where:

> **“The data is reliable enough — now where are the business problems?”**

### 🔥 One-Line Summary

The dataset passes all structural and integrity checks, making it reliable for analysis, while still containing realistic behavioral and risk patterns (such as unreported fraud and multi-device usage) that can be further investigated for business insights.
