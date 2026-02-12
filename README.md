📡 Telecom Churn Analytics & Strategic Revenue Protection
📖 Executive Summary
In the telecommunications sector, the cost gap between customer acquisition and retention is staggering—acquisition can be 5x to 25x more expensive. This project moves the organization from a reactive "damage control" stance to a proactive "revenue protection" model. Using a Random Forest ensemble and advanced data balancing (SMOTE), this pipeline identifies at-risk customers with 71% recall, specifically isolating 400 High-Value VIPs who represent the greatest financial threat to the organization.

🛠️ The Technical Pipeline
1. Data Engineering & Preprocessing

The raw dataset (7,043 records) required significant transformation to be model-ready:

Type Coercion: TotalCharges was converted from string to numeric; 11 missing values for new customers were imputed with 0.

Feature Expansion: One-Hot Encoding was applied to categorical variables, resulting in a 31-dimensional feature space.

Correlation Analysis: A heatmap was used to identify multicollinearity, specifically between MonthlyCharges and TotalCharges.

2. Addressing Class Imbalance (SMOTE)

The original data was imbalanced (3:1 ratio of loyalists to churners). A model trained on this would naturally bias toward "No Churn."

The Solution: I implemented Synthetic Minority Over-sampling Technique (SMOTE).

Result: Balanced the training set to 3,892 samples per class, allowing the model to learn the specific boundary between staying and leaving.

3. Model Architecture: Random Forest

I selected a Random Forest Classifier (100 estimators, max depth 10) for its ability to handle non-linear interactions and its robustness against outliers. It effectively identifies "Interacted Risks," such as a customer having a high bill and a month-to-month contract.

📊 Performance & Analysis
Model Metrics

Metric	Result	Business Value
Accuracy	79.27%	High overall reliability.
Recall	71.00%	Successfully catches 7 out of 10 actual churners.
Precision	60.00%	Minimizes wasted retention budget.
Key Drivers of Churn

Tenure: The first 6 months are the "Danger Zone."

Payment Method: Electronic Check users churn significantly faster due to "Payment Friction."

Contract Type: Month-to-month contracts are the strongest individual risk factor.

🎯 The Strategic Risk Quadrant
The "Hero Visual" of this project is the Risk-Value Quadrant. By mapping churn probability against monthly revenue, we segmented customers into four actionable groups:

VIPs at Risk (400 Customers): The high-priority "Hit List." High revenue + high risk.

Safe VIPs (484 Customers): High revenue + low risk. Ideal for upselling.

Low-Value Risk: Managed via low-cost automated emails.

Standard Customers: The stable core of the business.

🚀 Deployment & Recommendations
Targeted Outreach: Launch a high-touch loyalty campaign for the 400 VIPs at Risk.

Friction Reduction: Incentivize Electronic Check users to switch to Autopay.

Retraining Loop: Implement a monthly retraining cycle to adapt to new competitor pricing and market trends.

📂 Project Structure
Strategic_Retention_Analysis.ipynb: Full Python source code.

requirements.txt: Necessary libraries (Pandas, Scikit-learn, Imbalanced-learn).

whitepaper.md: Detailed technical and business report.

images/: Generated PNG files for all 4 project visuals.

💻 Installation
Bash
# Clone the repository
git clone https://github.com/mupparaju1985/telecom-churn-prediction.git

# Install dependencies
pip install -r requirements.txt

# Run the model
python Strategic_Retention_Analysis.ipynb


#Author: Balakrishna Mupparaju
