# 🕵️ Insurance Fraud Detection


## 📌 Project Description

Insurance fraud is a serious and costly issue that affects the entire industry. In this project, we aim to build a machine learning model that can detect fraudulent insurance claims based on a variety of customer, policy, and incident features. The goal is to help insurance companies better identify and investigate suspicious claims, reduce financial losses, and improve overall operational efficiency.

## 📂 Dataset


The dataset used in this project is a synthetic auto insurance claims dataset, provided as part of a case study. It includes the following types of features:


**Categorical variables**
    - **Policy_state**: refers to the U.S. state in which the insurance policy was issued or registered.
    - **Policy_csl**: Combined Single Limit is the maximum amount an insurance company will pay for liability (bodily injury + property damage) per accident, regardless of how the money is split. Example: policy_csl = "250/500". This may refer to $250,000 per person and $500,000 per accident.
    - **insured_sex**: sex of the insured person.
    - **insured_education_level**: Education level of the insured person.
    - **insured_occupation**: refers to the occupation or job title of the insured person (the person holding the insurance policy).
    - **insured_hobbies**: hobbies of the insured person.
    - **insured_relationship**: describes the relationship of the insured person to the primary policyholder.
    - **incident_type**: describes the nature or category of the insurance claim event.
    - **collision_type**: specifies the kind of impact or collision that occurred during the incident.
    - **incident_severity**: represents the level of damage or seriousness associated with the insurance incident.
    - **authorities_contacted**: indicates which authority (if any) was notified or involved during the insurance incident.
    - **incident_state**: refers to the U.S. state where the incident (e.g., accident, theft, etc.) occurred.
    - **incident_city**: refers to the U.S. city where the incident (e.g., accident, theft, etc.) occurred.
    - **incident_location**: The variable incident_location indicates the specific city or place where the insurance incident occurred.
    - **property_damage**: indicates whether the insurance incident involved damage to property other than the insured vehicle.
    - **police_report_available**: indicates whether a police report was filed and available in connection with the insurance claim.
    - **auto_make**: The variable auto_make refers to the manufacturer (brand) of the insured vehicle involved in the incident.
    - **auto_model**: refers to the specific model of the insured vehicle involved in the claim. It gives more detail than auto_make (which is the brand or manufacturer).


 **Numeric variables**  
    - **months_as_customer**: represents the number of months the person has been a customer of the insurance company.
    - **Age**: The variable age represents the age of the insured person.
    - **policy_number**: ID of policy.
    - **policy_deductible**: refers to the deductible amount set in the insurance policy.
    - **policy_annual_premium**: represents the total amount the customer pays for their insurance policy per year.
    - **umbrella_limit**: refers to the amount of additional liability coverage provided by an umbrella insurance policy
    - **insured_zip**: refers to the ZIP code (postal code) of the insured person's address — typically the residence location of the policyholder.
    - **capital-gains**: refers to the amount of money gained from the sale of capital assets, such as property, stocks, or other investments.
    - **capital-loss**: refers to the amount of money lost from the sale of capital assets, such as property, stocks, or other investments.
    - **incident_hour_of_the_day**: represents the hour when the insurance-related incident occurred, typically using a 24-hour clock format.
    - **number_of_vehicles_involved**: represents the total number of vehicles involved in the insurance incident.
    - **bodily_injuries**: Total number of injured persons.
    - **witnesses**: represents the number of people who witnessed the incident.
    - **total_claim_amount**: refers to the total monetary value of the insurance claim submitted for a particular incident.
    - **injury_claim**: refers to the portion of the total claim amount that is attributed to bodily injury.
    - **property_claim**: represents the amount of the total insurance claim related to property damage.
    - **auto_year**: represents the portion of the total insurance claim that is related to vehicle damage — that is, the repair or replacement costs   of the insured vehicle resulting from the incident.
    - **auto_year**: efers to the manufacturing year of the insured vehicle.
    - **policy_bind_year**: refers to the year when the insurance policy was activated or bound — in other words, the start year of the coverage agreement between the insured person and the insurance company.

**Datetime Variables**: 

    - **policy_bind_date**:  is the date when the insurance policy started.
    - **incident_date**: is the date when the insurance incident occurred


**Target Variable**: fraud_reported (Y/N)

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