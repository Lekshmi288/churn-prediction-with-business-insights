# Customer Churn Prediction with Business Insights and ROI Analysis

This project presents an end-to-end machine learning pipeline for predicting customer churn in a telecom company and translating those predictions into actionable retention strategies. The focus is not only on predictive performance but also on understanding **why customers churn** and how to **prioritize high-risk, high-value customers** to maximize retention ROI.

---

## 💼 Project Overview

- **Domain**: Telecom
- **Goal**: Predict customer churn, estimate revenue at risk, and guide retention strategy
- **Model Used**: RandomForestClassifier
- **Key Techniques**:
  - Churn prediction using supervised learning
  - Model explainability with SHAP
  - Customer segmentation based on risk and value
  - Cost-benefit and ROI simulation
  - Actionable insights for business decision-making

---

## 🧪 Workflow

1. **Data Loading and Cleaning**  
   Loaded and preprocessed customer data, handled categorical encoding and missing values.

2. **Exploratory Data Analysis and Preprocessing**
   - Explored churn patterns across demographic and service-related features
   - Visualized correlations between contract type, service usage, and churn behavior

3. **Model Training & Evaluation**
   - Trained a Random Forest Classifier to predict churn
   - Evaluated on test set:
     - **Precision**: 0.50
     - **Recall**: 0.87
     - **Accuracy**: ~73%
   - Business-framed interpretation of precision-recall tradeoff

4. **Model Explainability with SHAP**
   - Used SHAP (SHapley Additive exPlanations) for feature attribution
   - Visualized global feature importance and local explanations
   - Key drivers of churn: monthly contracts, high monthly charges, Fibre optics as the internet provider, manual payment methods, lack of tech support/online security/device protection etc.

5. **Churn Probability and Revenue at Risk**
   - Estimated 12-month revenue at risk using churn probabilities × MonthlyCharges × 12
   - Total predicted revenue at risk: **$267,999**

6. **Segment-Level Churn Insights**
   - Segmented customers into:
     - **High-Risk High-Tier (HRHT)**: Churn prob > 0.5 and revenue > $500/year
     - **High-Risk Low-Tier (HRLT)**: Churn prob > 0.5 and revenue ≤ $500/year
   - HRHT customers (n = 238) account for:
     - **~66% of total revenue at risk**
     - **~87% of revenue risk among high-risk customers**

7. **Actionable Insights for Customer Retention**
   - Retention strategy focused on HRHT customers
   - Simulated retention effort:
     - Cost: $50 per customer
     - Success rate: 40%
     - **ROI ≈ 5x**
   - Ideal-case ROI (with ground truth): **~17x**
   - Strategic recommendations:
     - Incentivize annual contracts and autopay
     - Bundle value-added services (e.g. tech support, streaming)
     - Target single users with referral/family plans

---

## 💰 Evaluation-Based ROI (Ground Truth Scenario)

Using actual churn labels from the test set, we performed a cost-benefit analysis to measure how the model performs in an ideal evaluation setting.

| Metric                                     | Value         |
| ----------------------------------------- | ------------- |
| Recall                                     | 0.87          |
| Precision                                  | 0.50          |
| Revenue Saved (True Positives)             | \$145,607.55  |
| Cost of Missed Churners (False Negatives)  | \$21,757.45   |
| Cost of Unnecessary Retention efforts (False Positives) | \$8,200  |
| Net Revenue Retained                       | \$137,407.55  |
| ROI                                        | ~17x          |

> Despite moderate precision, the model delivers high business value by capturing most of the churners with significant revenue impact.

----

## 💡 Key Insights

We identified 238 High-Risk, High-Tier (HRHT) customers — those with churn probability > 0.5 and annual revenue > $500 — who:

- Represent ~66% of the total predicted revenue at risk
- Contribute ~87% of the risk among high-risk customers

Even without knowing who will churn, targeting this group with a $50 retention offer and assuming a 40% success rate yields:

- **Revenue saved**: ~$70,500  
- **Net profit**: ~$58,600  
- **ROI**: ~5x  

In an ideal scenario (with the ground truth churn label data), ROI rises to ~17x.

The model enables revenue-focused prioritization, helping the business focus on customers **whose churn would have the greatest financial impact.**

Even with model precision around 50%, meaning roughly half of the targeted HRHT customers may not churn, the retention strategy remains profitable:

- ~50% of retention spend may be “wasted” on false positives
- However, ROI stays positive because the **retained customers contribute significantly more revenue than the cost of outreach**
  
This validates the model’s **value in prioritizing customer retention**, even under realistic business constraints.

----

## 📁 Repository Contents

- `customer-churn-risk-analysis.ipynb`: Complete notebook with EDA, modeling, SHAP, ROI simulation, and insights
- `model/`: Saved model
- `README.md`: Project overview

---

## Potential Extensions

- Include time-based features for retention timing strategies

---

## 🧰 Tech Stack

- Python
- pandas, NumPy
- scikit-learn
- matplotlib, seaborn
- SHAP

---

