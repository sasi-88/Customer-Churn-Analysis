# Customer-Churn-Analysis

## Project Overview
Customer Churn Analysis is a Power BI project designed to identify customer retention patterns and analyze the factors that influence customer attrition. The dashboard provides actionable insights into customer behavior, helping businesses reduce churn and improve customer retention strategies.

## Objectives
- Analyze customer churn trends.
- Identify high-risk customer segments.
- Evaluate the impact of contracts, services, and payment methods on churn.
- Estimate potential revenue loss due to customer attrition.
- Support data-driven business decision-making.

## Dataset
The project uses the Telco Customer Churn dataset from Kaggle.

Dataset Link:
https://www.kaggle.com/datasets/blastchar/telco-customer-churn

### Dataset Features
- Customer Demographics
- Contract Type
- Internet Services
- Payment Methods
- Monthly Charges
- Total Charges
- Customer Tenure
- Churn Status

## Tools & Technologies
- Power BI Desktop
- Power Query
- DAX (Data Analysis Expressions)
- CSV Dataset
- GitHub

## Data Cleaning & Transformation
The following preprocessing steps were performed:

- Converted TotalCharges to Decimal Number.
- Removed rows with invalid or blank TotalCharges values.
- Created a ChurnFlag column for numerical analysis.
- Replaced SeniorCitizen values (0/1) with No/Yes labels.
- Validated data types and removed inconsistencies.

## DAX Measures

### Total Customers
```DAX
Total Customers =
COUNTROWS('telco-customer-churn')
```

### Churned Customers
```DAX
Churned Customers =
CALCULATE(
    COUNTROWS('telco-customer-churn'),
    'telco-customer-churn'[Churn] = "Yes"
)
```

### Churn Rate %
```DAX
Churn Rate % =
DIVIDE(
    [Churned Customers],
    [Total Customers]
) * 100
```

### Average Monthly Charges
```DAX
Avg Monthly Charges =
AVERAGE('telco-customer-churn'[MonthlyCharges])
```

### Average Tenure
```DAX
Avg Tenure (Months) =
AVERAGE('telco-customer-churn'[tenure])
```

### Revenue at Risk
```DAX
Revenue at Risk =
CALCULATE(
    SUM('telco-customer-churn'[MonthlyCharges]),
    'telco-customer-churn'[Churn] = "Yes"
)
```

## Dashboard Pages

### Page 1: Executive Overview
Features:
- Total Customers KPI
- Churn Rate KPI
- Revenue at Risk KPI
- Churned vs Retained Customers
- Churn by Contract Type
- Churn by Internet Service

### Page 2: Customer Risk Analysis
Features:
- Churn by Tenure Group
- Churn by Payment Method
- Contract vs Senior Citizen Analysis
- Interactive Slicers

### Page 3: Insights & Findings
Features:
- Service Usage Analysis
- Monthly Charges Comparison
- Business Recommendations
- Key Customer Retention Insights

## Key Insights
- Month-to-month contract customers show significantly higher churn rates.
- Customers with shorter tenure are more likely to leave.
- Customers without Online Security services have a higher probability of churn.
- Revenue loss can be estimated by analyzing churned customers' monthly charges.

## Project Structure
```
Customer-Churn-Analysis/
│
├── Dataset/
│   └── WA_Fn-UseC_-Telco-Customer-Churn.csv
│
├── PowerBI/
│   └── Customer_Churn_Analysis.pbix
│
├── Screenshots/
│   ├── Executive_Overview.png
│   ├── Customer_Risk_Analysis.png
│   └── Insights_and_Findings.png
│
└── README.md
```
## Future Enhancements
- Customer Churn Prediction using Machine Learning.
- Real-time dashboard integration.
- Advanced customer segmentation.
- Automated retention recommendations.

## Author
**Sasidhar Maddineni**

GitHub: https://github.com/sasi-88

---
⭐ If you found this project useful, consider giving it a star.
