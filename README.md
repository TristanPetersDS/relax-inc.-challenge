# Predicting User Adoption

This repository contains a data science project focused on identifying the key factors that predict user adoption for a software product. By analyzing user profile data and daily engagement logs, this project builds a machine learning model to uncover what drives a user to become "adopted."

An **"adopted user"** is defined as a user who logs into the product on three separate days within any seven-day period.

## 🚀 Key Findings & Insights

The analysis revealed that the most significant predictors of user adoption are:

* **Account Tenure**: The length of time a user has maintained their account is the strongest indicator of adoption. This highlights the importance of long-term user value and retention.
* **Last Login Recency**: Users who have logged in recently are far more likely to be classified as "adopted." This underscores the momentum of engagement.
* **Creation Source**: The method by which a user's account was created (e.g., invited by another user, signed up via the website) is a significant factor. Users invited to an organization (`ORG_INVITE`) showed a higher tendency for adoption.
* **Marketing Engagement**: While less impactful than the above, whether a user opted into mailing lists or marketing drips still holds some predictive power.

## 🛠️ Approach

The project followed a structured data science workflow:

1.  **Data Cleaning & Preprocessing**:
    * Loaded and merged two datasets: user information and daily engagement logs.
    * Handled missing values and converted timestamp columns to the correct `datetime` format for analysis.

2.  **Feature Engineering**:
    * Created the primary target variable, `adopted_user`, by implementing a function to check each user's login history against the "3 logins in 7 days" criteria.
    * Engineered additional features like `account_age_days` to capture the tenure of each user.

3.  **Exploratory Data Analysis (EDA)**:
    * Visualized the distribution of adopted vs. non-adopted users.
    * Analyzed the relationship between categorical features (like `creation_source`) and user adoption to uncover initial trends.

4.  **Predictive Modeling**:
    * A **Random Forest Classifier** was chosen for its robustness and ability to provide clear feature importance scores.
    * The model was trained on the preprocessed data to predict the `adopted_user` status.
    * The model's performance was evaluated, and feature importances were extracted to identify the key predictive factors.
