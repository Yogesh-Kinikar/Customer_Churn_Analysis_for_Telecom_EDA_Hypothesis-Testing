
# Customer-Churn-Analysis-for-Telecom-EDA-Hypothesis-Testing

Detailed analysis of the telecom customer churn dataset. Includes data cleaning, EDA, univariate/bivariate analysis in Python, and hypothesis tests (Two-Proportion Z-Test, ANOVA) to uncover churn drivers and recommend retention strategies.

---

# 📊 Customer Churn Analysis

## **Overview**
This project provides a comprehensive analysis of customer churn in the telecom industry using Python. The dataset includes customer demographics, service details, contract types, payment methods, and churn status. Key insights reveal that most customers have tenure under 55 months, the average monthly charge is **\$64.76**, and a significant portion (25%) pays more than **\$90/month**, which correlates with higher churn risk.


---

## **Key Observations**

1. **Senior Citizens Exhibit Higher Churn Risk**
   - Senior citizens churn at **42%**, significantly higher than other segments.
<img width="1007" height="631" alt="image" src="https://github.com/user-attachments/assets/5b31b796-ff76-46c8-b65c-a87030d5d312" />



2. **🧪 Hypothesis Testing — Two‑Proportion Z‑Test (Seniors vs Non‑Seniors)**
   - **Why:** Quantifies if senior citizens truly churn more than others (observed churn rate: 42%).
   - **H₀ (Null):** No difference in churn rates between senior and non-senior customers *(P_senior = P_non‑senior)*  
   - **H₁ (Alternative):** A significant difference exists *(P_senior ≠ P_non‑senior)*
   - **Result:** p-value < 0.001; Odds Ratio (OR) = **2.31**; 95% CI **[2.02 – 2.63]**
   - **Conclusion**: Reject H₀. A significant difference exists in Churn rate for Senior citizen vs other customers
   - ✅ Interpretation: Senior citizens churn significantly more and should be prioritized for retention programs.
<img width="1316" height="343" alt="image" src="https://github.com/user-attachments/assets/026769f7-a787-4164-9729-2ac20ceaed33" />



3. **Fiber Optic Customers Are More Prone to Churn**
   - Fiber Optic users churn at **42%**, indicating service type strongly correlates with attrition. 
<img width="1008" height="635" alt="image" src="https://github.com/user-attachments/assets/7e49fb34-80fa-43c6-aaf6-c451c5611128" />




4. **Contract Type Strongly Influences Churn**
   - Month-to-month: **43% churn**
   - One-year: **11% churn**
   - Two-year: **3% churn**
   - ✅ Long-term contracts significantly improve retention.
<img width="1000" height="625" alt="image" src="https://github.com/user-attachments/assets/b408aba2-cf87-463b-9354-2bd66b48f277" />



5. **Monthly Charges Differ by Contract Type**
   - One-Way ANOVA confirms a significant difference in monthly charges across contract types
   - H₀: Mean MonthlyCharges is equal across contract types.
   - H₁: At least one contract type has a different mean.
   - Results: ANOVA (MonthlyCharges ~ Contract): F=20.83, p=9.5753e-10
   - **Conclusion:** Reject H₀. Monthly charges **do vary** by contract type.
<img width="1125" height="548" alt="image" src="https://github.com/user-attachments/assets/a8a8166c-9f02-4a14-bf73-a881c75d06f2" />

   - **Tukey HSD Findings:**
     - Two-year contracts have significantly lower monthly charges than month-to-month and one-year contracts.
     - No significant difference between month-to-month and one-year contracts.
<img width="922" height="418" alt="image" src="https://github.com/user-attachments/assets/ffed55cc-4569-4373-be30-2a66a7cd6d67" />




6. **Payment Method Correlates with Churn**
   - Electronic check users churn at **45%**, vs. 15–19% for other payment methods.
   - ✅ Electronic check customers are a high-risk segment.
<img width="1003" height="625" alt="image" src="https://github.com/user-attachments/assets/8e419595-945f-475a-8b95-d9ced9867f7c" />



7. **Tenure Is a Strong Predictor of Churn**
   - 1–12 months: **47% churn**
   - 13–24 months: **28% churn**
   - 25–36 months: **21% churn**
   - 61–72 months: **6% churn**
   - ✅ Focus retention efforts on early-stage customers.
<img width="1001" height="626" alt="image" src="https://github.com/user-attachments/assets/dfc69db4-734e-4e0e-bf70-2bfc44fe9831" />



8. **Pricing Impact**
   - Higher monthly charges → higher churn.
<img width="757" height="578" alt="image" src="https://github.com/user-attachments/assets/73b3310b-cd73-4431-9ad3-ab97ffb2a011" />


   - Higher total charges → lower churn (due to longer tenure).   
<img width="752" height="582" alt="image" src="https://github.com/user-attachments/assets/33940dd3-e890-447c-b91a-f06de55d2195" />



9. **Feature Correlation Analysis**
- **Contract type** is the strongest predictor of churn:  
  - Month-to-month contracts show the highest positive correlation with churn.  
  - Two-year contracts have the strongest negative correlation, indicating high retention.
- Other churn drivers include:  
  - Lack of **Online Security** and **Tech Support**  
  - **Electronic check** payment method  
  - **Fiber optic** internet service  
  - Short tenure (1–12 months) and high monthly charges.
- Features like **gender**, **phone service**, and **multiple lines** have near-zero correlation, meaning they have little impact on churn. 
<img width="717" height="759" alt="image" src="https://github.com/user-attachments/assets/46f8ef7c-e528-44fb-8171-13ce4cc38173" />



---

## **Statistical Tests**
### ✅ Two-Proportion Z-Test: Senior vs Non-Senior Churn
- **H₀:** No difference in churn rates.
- **Result:** *p < 0.001*, OR = 2.31 → Seniors churn significantly more.

### ✅ One-Way ANOVA: Monthly Charges by Contract Type
- **H₀:** Mean monthly charges equal across contract types.
- **Result:** F = 20.83, *p ≈ 9.6e-10* → Significant difference exists.
- **Tukey HSD:**  
  - Two-year contracts have significantly lower charges than month-to-month and one-year.
  - Month-to-month vs one-year → No significant difference.

---

## **Business Recommendations**
✔ **Retention Programs for Seniors**  
   - Offer loyalty discounts, personalized support, and simplified billing.

✔ **Promote Long-Term Contracts**  
   - Incentivize upgrades from month-to-month to annual or biennial plans.

✔ **Address Fiber Optic Churn**  
   - Investigate service quality issues and improve customer experience.

✔ **Reduce Electronic Check Risk**  
   - Encourage secure, automated payment methods (credit card, bank transfer).

✔ **Early Tenure Engagement**  
   - Implement onboarding programs, proactive support, and targeted offers for customers in their first year.

✔ **Price Optimization**  
   - Review pricing for high monthly charge customers to prevent churn.

---

## **Next Steps**
- Build predictive churn model using logistic regression or tree-based algorithms.
- Deploy retention strategy dashboard for real-time monitoring.
- Segment customers for targeted marketing campaigns.

---

### **Project Credits**
This project is done by **Yogesh Kinikar** (Credits: **Data Science course by Dr. Satyajit Pattnaik**)

---
