# 🕵️ Insurance Fraud Detection


## 📌 Project Description

Insurance fraud is a serious and costly issue that affects the entire industry. In this project, we aim to build a machine learning model that can detect fraudulent insurance claims based on a variety of customer, policy, and incident features. The goal is to help insurance companies better identify and investigate suspicious claims, reduce financial losses, and improve overall operational efficiency.

## 📂 Dataset


The dataset used in this project is a synthetic auto insurance claims dataset, provided as part of a case study. It includes the following types of features:


## Categorical Variables

- **policy_state**: Refers to the U.S. state in which the insurance policy was issued or registered.
- **policy_csl**: Combined Single Limit – maximum liability per accident (e.g., "250/500" = $250,000 per person and $500,000 per accident).
- **insured_sex**: Sex of the insured person.
- **insured_education_level**: Education level of the insured person.
- **insured_occupation**: Occupation or job title of the insured person.
- **insured_hobbies**: Hobbies of the insured person.
- **insured_relationship**: Relationship of the insured person to the primary policyholder.
- **incident_type**: Nature or category of the insurance claim event.
- **collision_type**: Kind of impact or collision during the incident.
- **incident_severity**: Level of damage or seriousness of the incident.
- **authorities_contacted**: Which authority (if any) was notified or involved.
- **incident_state**: U.S. state where the incident occurred.
- **incident_city**: U.S. city where the incident occurred.
- **incident_location**: Specific city or place where the incident occurred.
- **property_damage**: Whether property damage occurred other than to the insured vehicle.
- **police_report_available**: Whether a police report was filed.
- **auto_make**: Manufacturer (brand) of the insured vehicle.
- **auto_model**: Specific model of the insured vehicle.

## Numeric Variables

- **months_as_customer**: Number of months the person has been a customer.
- **age**: Age of the insured person.
- **policy_number**: ID of the insurance policy.
- **policy_deductible**: Deductible amount in the policy.
- **policy_annual_premium**: Yearly premium paid by the customer.
- **umbrella_limit**: Additional liability coverage from umbrella policy.
- **insured_zip**: ZIP code of the insured person’s residence.
- **capital-gains**: Profit from sale of capital assets.
- **capital-loss**: Loss from sale of capital assets.
- **incident_hour_of_the_day**: Hour when the incident occurred (24-hour clock).
- **number_of_vehicles_involved**: Total number of vehicles in the incident.
- **bodily_injuries**: Number of injured persons.
- **witnesses**: Number of people who witnessed the incident.
- **total_claim_amount**: Total value of the insurance claim.
- **injury_claim**: Portion of the claim related to bodily injury.
- **property_claim**: Portion of the claim related to property damage.
- **auto_year**: Manufacturing year of the insured vehicle.
- **policy_bind_year**: Year when the insurance policy started.

## Datetime Variables

- **policy_bind_date**: Date when the insurance policy was activated.
- **incident_date**: Date when the incident occurred.

## Target Variable

- **fraud_reported**: Indicates whether the incident was reported as fraud (Y/N).


## 🛠️ Project Pipeline

The project follows a standard data science workflow:

1. **Exploratory Data Analysis (EDA)**  
   - Summary statistics, missing values, feature distributions  
   - Chi² tests for categorical features  
   - Correlation analysis for numerical features  
   - Cramér’s V matrix for categorical feature dependencies

2. **Preprocessing**  
   - Handling missing values  
   - Encoding categorical variables (Label Encoding, One-Hot Encoding)  
   - SMOTE for class imbalance (fraud cases are underrepresented)

3. **Modeling**  
   - Model: GradientBoostingClassifier,  Random Forest 
   - Pipeline includes SMOTE and preprocessing  
   - Hyperparameter tuning with GridSearchCV` 
   - Evaluation metrics: accuracy, precision, recall, F1-score, ROC AUC

4. **Evaluation**  
   - Classification report and confusion matrix  
   - ROC and Precision-Recall curves  
   - Feature importance ranking


## 🧠 Key Learnings

- Fraud detection is a class imbalance problem — metrics like **ROC AUC** and **Recall** are more useful than accuracy.
- Categorical feature encoding and thoughtful preprocessing significantly impact model performance.
- Gradient Boosting performs well with mixed-type tabular data and imbalanced classes.

## 📌 Future Work

- Try other models: XGBoost, CatBoost, Logistic Regression  
- Use SHAP or LIME for better interpretability  
- Integrate real-time prediction interface (e.g., Flask app)