# 📈 Ecommerce Revenue Optimization: From Prioritization to A/B Testing

## 🎯 Project Overview
This project focuses on boosting revenue for an online store through a dual-phase analytical approach. First, I prioritized growth hypotheses using industry-standard frameworks (**ICE/RICE**). Second, I analyzed an **A/B Test** to determine if specific changes led to statistically significant improvements in conversion and average order size.



## 🧪 Phase 1: Hypothesis Prioritization
I evaluated 9 business hypotheses by calculating their **ICE** and **RICE** scores. 
* **Key Insight:** The "Add a subscription form to all main pages" hypothesis jumped to the top rank when using **RICE** due to its massive **Reach**, demonstrating why accounting for user volume is critical for ROI.

## 📊 Phase 2: A/B Test Analysis
The test compared a control group (A) against a treatment group (B). The analysis included:
* **Cumulative Metrics:** Tracking conversion rates and average order size over time to ensure stability.
* **Statistical Significance:** Using **Shapiro-Wilk** and **Mann-Whitney U tests** to validate results.
* **Anomaly Handling:** Identified and removed outliers (top 1% of users by frequency and spend) that were skewing the revenue data.



## 💡 Results & Business Impact
| Metric | Raw Data Difference | Filtered Data Difference | Statistical Significance |
| :--- | :--- | :--- | :--- |
| **Conversion Rate** | **+13.8%** | **+13.1%** | ✅ Significant (p < 0.05) |
| **Avg. Order Size** | +25.2% | -1.4% | ❌ Not Significant |

**Conclusion:** The experiment was a success in terms of **Conversion**. The 13% lift in conversion is robust and remains stable after removing outliers. Although the average order size didn't increase, the higher conversion volume justifies a full rollout of version B.



## 🚀 Final Recommendation
* **Stop the test:** Group B is the clear winner in conversion.
* **Rollout:** Implement the new version for 100% of the traffic.
* **Next Steps:** Focus on a new A/B test specifically designed to increase the Average Ticket Value (Up-selling/Cross-selling).

## 🛠️ Tech Stack
* **Python:** Core analysis.
* **SciPy.stats:** For rigorous statistical testing.
* **Pandas & NumPy:** Data manipulation and filtering.
* **Matplotlib & Seaborn:** Statistical visualization.
