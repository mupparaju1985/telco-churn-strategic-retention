Telecom Churn Prediction: A Value-Based Machine Learning Approach
📌 Project Overview
In the telecommunications industry, acquiring a new customer is 5x to 25x more expensive than retaining an existing one. This project utilizes machine learning to transition from a reactive "damage control" strategy to a proactive "revenue protection" model. By predicting churn probability and mapping it against customer value, we identify the 400 "VIPs at Risk" who represent the highest financial threat to the organization.

📊 Key Results
Recall: 71% (Successfully identified 7 out of 10 actual churners).

Accuracy: 79.27% on the test set.

Business Impact: Segmented 400 High-Value VIPs for immediate retention outreach.

Data Balancing: Overcame a 3:1 class imbalance using SMOTE.

🛠️ Technical Workflow
1. Data Engineering & Preprocessing

Numeric Coercion: Converted TotalCharges from string objects to numeric floats.

Imputation: Handled missing values for new customers with zero tenure.

Categorical Encoding: Applied One-Hot Encoding to transform 21 raw features into a 31-dimensional feature space.

2. Handling Class Imbalance (SMOTE)

To prevent the model from biasing toward the majority class (non-churners), I implemented Synthetic Minority Over-sampling Technique (SMOTE). This balanced the training set to an equal 3,892 samples per class, significantly improving the model's ability to "catch" churners (Recall).

3. Model Architecture

I deployed a Random Forest Classifier (100 estimators, max depth 10). This ensemble approach was chosen for its:

Robustness against multicollinearity (Monthly vs. Total Charges).

Ability to capture non-linear interactions (e.g., how Month-to-Month contracts interact with Fiber Optic service).


Shutterstock
📈 Strategic Insights: The Risk-Value Quadrant
The most actionable part of the project is the Strategic Risk Quadrant. Instead of just predicting "Yes/No," the model generates a probability score. We mapped this score against Monthly Charges to prioritize retention efforts:

VIPs at Risk (400 Customers): High Monthly Revenue ($70+) + High Risk (>50%). Priority 1.

Safe VIPs (484 Customers): High Revenue + Low Risk. Upsell targets.

Low-Value Risk (166 Customers): High Risk + Low Revenue. Automated monitoring.

🚀 How to Use
Clone the Repo:

Bash
git clone https://github.com/mupparaju1985/telecom-churn-prediction.git
Install Dependencies:

Bash
pip install pandas scikit-learn matplotlib seaborn imbalanced-learn
Run the Analysis:

Bash
python churn_analysis.py
📂 Project Structure
churn_analysis.py: The main Python script containing the full pipeline.

Mupparaju_Final_WhitePaper.pdf: The detailed business report.

visualizations/: Folder containing the Heatmap, Feature Importance, and Risk Quadrant plots.

📝 Conclusion & Recommendations
The analysis proves that Tenure and Payment Method (specifically Electronic Checks) are the primary drivers of churn.

Recommendation 1: Move "Electronic Check" users to "Autopay" to reduce payment friction.

Recommendation 2: Targeted loyalty offers for the 400 VIPs at Risk to move them into annual contracts.

Author: Balakrishna Mupparaju
