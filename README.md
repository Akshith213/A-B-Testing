# A/B Testing Analysis Report

![Python](https://img.shields.io/badge/Python-3.8%2B-blue.svg)
![Libraries](https://img.shields.io/badge/Libraries-Pandas%2C%20NumPy%2C%20SciPy%2C%20Statsmodels-green)
![License](https://img.shields.io/badge/License-MIT-yellow.svg)

## 📚 Overview

Welcome to my **A/B Testing Analysis Report**! In this project, I conducted an A/B test to evaluate the effectiveness of a new variant (Test group) compared to the existing version (Control group) across several key business metrics. The primary objective was to determine whether the changes implemented in the Test group positively influenced user behavior and business outcomes.

## 🎯 Objectives

- **Evaluate Key Metrics:** Assess the impact of the Test variant on critical business metrics such as Conversion Rate, Click-Through Rate (CTR), Spend, and user engagement actions.
- **Statistical Validation:** Use appropriate statistical tests to determine the significance of observed differences between Control and Test groups.
- **Understand Effect Sizes:** Calculate effect sizes to gauge the practical significance of the Test variant's impact.
- **Provide Actionable Insights:** Offer recommendations based on the findings to inform business decisions and future testing strategies.

## 🛠️ Technologies Used

- **Programming Language:** Python 3.8+
- **Libraries:**
  - [Pandas](https://pandas.pydata.org/)
  - [NumPy](https://numpy.org/)
  - [SciPy](https://www.scipy.org/)
  - [Statsmodels](https://www.statsmodels.org/)
  - [Matplotlib](https://matplotlib.org/)
  - [Seaborn](https://seaborn.pydata.org/)

## 📈 Methodology

### **1. Data Collection**

I collected data on seven metrics from both Control and Test groups:

1. **Conversion Rate (%)**
2. **Click-Through Rate (CTR %)**
3. **Spend [USD]**
4. **# of Website Clicks**
5. **# of View Content**
6. **# of Add to Cart**
7. **# of Purchase**

### **2. Statistical Tests**

To analyze the data, I performed the following statistical tests:

- **Mann-Whitney U Test:** Used for metrics that did not follow a normal distribution.
- **Independent Two-Sample t-Test:** Applied to metrics with normally distributed data.

To account for multiple comparisons and reduce the risk of false positives, I applied the **Bonferroni correction** to adjust the p-values.

Additionally, I calculated effect sizes to understand the magnitude of the differences between the groups:

- **Rank-Biserial Correlation:** For metrics tested with the Mann-Whitney U Test.
- **Cohen's d:** For metrics tested with the Independent Two-Sample t-Test.

## 📝 Results

### **Statistical Test Outcomes**

| Metric               | Test Type                     | Statistic | p-value  | p-value_corrected | Reject H0 | Effect Size |
|----------------------|-------------------------------|-----------|----------|--------------------|-----------|-------------|
| Conversion Rate (%)  | Mann-Whitney U Test           | 520.00    | 0.304177 | 1.000000           | False     | -0.1556     |
| CTR (%)              | Mann-Whitney U Test           | 203.00    | 0.000268 | 0.001876           | True      | 0.5489      |
| Spend [USD]          | Independent Two-Sample t-Test | -2.969992 | 0.004326 | 0.030284           | True      | -0.7668     |
| # of Website Clicks  | Mann-Whitney U Test           | 350.00    | 0.141272 | 0.988904           | False     | 0.2222      |
| # of View Content    | Independent Two-Sample t-Test | 0.490301  | 0.625770 | 1.000000           | False     | 0.1266      |
| # of Add to Cart     | Mann-Whitney U Test           | 684.50    | 0.000541 | 0.003787           | True      | -0.5211     |
| # of Purchase        | Mann-Whitney U Test           | 454.00    | 0.958727 | 1.000000           | False     | -0.0089     |

### **Key Findings**

#### **1. Click-Through Rate (CTR %)**
- **Significance:** The Test group showed a significantly higher CTR compared to the Control group (p-value_corrected = 0.001876).
- **Effect Size:** A medium positive effect (0.55) indicates that the Test variant effectively increased user engagement.

#### **2. Spend [USD]**
- **Significance:** Users in the Test group spent significantly more money than those in the Control group (p-value_corrected = 0.030284).
- **Effect Size:** A large negative effect (-0.77) suggests that the Test variant had a substantial positive impact on spending behavior.

#### **3. # of Add to Cart**
- **Significance:** There was a significant decrease in the number of "Add to Cart" actions in the Test group (p-value_corrected = 0.003787).
- **Effect Size:** A medium negative effect (-0.52) indicates that while users spent more, they were less likely to add items to their carts.

#### **4. Non-Significant Metrics**
- **Conversion Rate (%)**, **# of Website Clicks**, **# of View Content**, and **# of Purchase** did not show significant differences between the Control and Test groups. This means the Test variant did not noticeably affect these aspects of user behavior.

### **Interpretation of Effect Sizes**

Effect sizes help in understanding the practical significance of the results:

- **Medium Effect Size (0.3 ≤ |d| < 0.8)**
  - **CTR % (0.55):** Indicates a moderate positive impact on user engagement.
  - **# of Add to Cart (-0.52):** Reflects a moderate negative impact on the number of items users add to their carts.

- **Large Effect Size (|d| ≥ 0.8)**
  - **Spend [USD] (-0.77):** Approaches a large effect, showing a strong positive influence on user spending.

- **Small or Negligible Effect Sizes**
  - **Conversion Rate (%) (-0.16)**, **# of Website Clicks (0.22)**, **# of View Content (0.13)**, and **# of Purchase (-0.01):** These values indicate minimal to no practical significance.

## 📊 Conclusion and Recommendations

### **Key Takeaways**

1. **Positive Impacts**
   - **CTR %:** The Test variant successfully increased the rate at which users clicked on content, indicating better engagement.
   - **Spend [USD]:** Users in the Test group spent more, suggesting enhanced revenue generation.

2. **Negative Impact**
   - **# of Add to Cart:** A decrease in "Add to Cart" actions may need further investigation to understand underlying causes, such as changes in user interface or user journey.

3. **No Significant Changes**
   - **Conversion Rate (%)**, **# of Website Clicks**, **# of View Content**, and **# of Purchase:** These metrics remained stable, indicating that the Test variant did not influence these specific aspects of user behavior.

### **Recommendations for Next Steps**

1. **Investigate "Add to Cart" Behavior**
   - Conduct user surveys or analyze session recordings to understand why the Test group added fewer items to their carts despite higher spending.
   - Review any design or functionality changes in the Test variant that might have influenced this behavior.

2. **Optimize Test Variant for Conversions**
   - While CTR and Spend improved, focus on strategies to enhance conversion rates. This could involve simplifying the checkout process or offering incentives to encourage purchases.

3. **Further Segmentation Analysis**
   - Analyze performance across different user segments (e.g., age groups, geographic locations) to identify if certain demographics responded differently to the Test variant.

4. **A/B Test Iteration**
   - Based on these findings, iterate on the Test variant to amplify positive outcomes (CTR and Spend) while addressing the decline in "Add to Cart" actions.
   - Consider running additional A/B tests focusing specifically on the checkout process to improve conversion rates.

5. **Monitor Long-Term Effects**
   - Assess whether the observed changes are sustained over time or if they were temporary fluctuations. Longitudinal studies can provide deeper insights into user behavior trends.

6. **Integrate Effect Sizes in Reporting**
   - When presenting results to stakeholders, include both p-values and effect sizes to convey both the statistical and practical significance of findings.

### **Final Thoughts**

The A/B testing results indicate that the Test variant positively influenced user engagement and spending but had an unintended negative impact on the number of "Add to Cart" actions. Balancing these outcomes will be crucial in optimizing the user experience and maximizing business performance. By addressing the identified areas and continuing to iterate based on data-driven insights, we can enhance the effectiveness of our strategies and achieve our business objectives.
