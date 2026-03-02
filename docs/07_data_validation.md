# Data Validation — FlowPay Risk Analysis

This document summarizes the data validation checks performed before analysis.

## 1. Validate Table Relationships (Data Integrity)

Goal:
Ensure transactions correctly reference valid entities.

---

Check: Transactions referencing missing users
Result: 0 issues found
Conclusion: Data integrity maintained

---

Check: Transactions referencing missing merchants
Result: 0 issues found
Conclusion: Merchant relationships valid

---

Check: Transactions referencing missing devices
Result: 0 issues found
Conclusion: Device relationships valid

---

Overall Status: PASS
No relational integrity issues detected.
Dataset is ready for analysis.
