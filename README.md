# Employee Satisfaction and Resignation Prediction

This project consists of two main tasks: predicting employee job satisfaction levels and predicting employee resignation using machine learning models. The dataset used for this project is part of an educational course and cannot be shared publicly.

## Research Goal

The goal of this research is to help the company minimize sudden employee attrition by predicting it through machine learning models. The project focuses on two main tasks:

1. Predicting employee job satisfaction levels.
2. Predicting whether an employee will resign from the company.

## Research Task #1: Predicting Employee Job Satisfaction Level

The first task involves predicting a continuous numerical feature, the **job satisfaction rate** of employees. The target variable is `job_satisfaction_rate`, and we used regression models for this task.

### Data Preparation and Analysis

- The training and test data were loaded, examined, and analyzed.
- Features were divided into categories: **categorical**, **discrete numerical**, and **continuous numerical**.
- During data exploration, relevant charts and histograms were created, and feature distributions were analyzed.
- Correlation matrices were built to study the relationships between features.
- The training data was split into training and validation sets in a **3:1 ratio**.

### Model Building

- **SMAPE** (Symmetric Mean Absolute Percentage Error) was used as a custom evaluation metric for this task.
- The following models were trained: **Linear Regression**, **DecisionTreeRegressor**, and **DecisionTreeRegressor** with different hyperparameters.
- A pipeline was built for data preparation, handling missing values, encoding, and scaling.
- After experimenting with different models and configurations, the best model was selected based on the SMAPE score.

### Best Model and Results

- **Best Model**: `DecisionTreeRegressor(max_depth=11, min_samples_leaf=2, min_samples_split=6, random_state=42)`
- **Best Model Cross-Validation Score**: 18.92  
- **SMAPE Score on the Test Set**: 14.34  

The adequacy of the best model was validated through comparison with a baseline model. The **SMAPE score** for the `DummyRegressor` was 38.81.

### Conclusions and Recommendations for the Business

- Focus on **employee performance ratings** given by supervisors, as they are a crucial factor for employee satisfaction.
- Employees with shorter tenures are likely to have lower satisfaction levels, so extra attention should be paid to newer employees.
- **Salary** has a noticeable impact on job satisfaction.
- **Labor contract violations** and **job level** rank 4th and 5th in importance for job satisfaction.

---

## Research Task #2: Predicting Employee Resignation

The second task involves predicting employee resignation, a binary classification problem where the target variable is `quit` (yes/no). We used classification models to predict whether an employee would leave the company.

### Data Preparation and Analysis

- The training and test data were loaded, examined, and analyzed.
- Features were divided into categories: **categorical**, **discrete numerical**, and **continuous numerical**.
- Correlation matrices were built and correlations between features were studied.
- A new feature, **employee satisfaction level**, was added from Task #1.
- The training data was split into training and validation sets in a **3:1 ratio**.
- A pipeline was built for data preparation, including handling missing values, encoding, and scaling.

### Model Building

- The following models were trained: **Logistic Regression**, **K-Nearest Neighbors**, **Support Vector Machines**, and **DecisionTreeClassifier** with different hyperparameters.
- The **ROC_AUC** metric was used for evaluating the classification models.
- After experimentation, the **DecisionTreeClassifier** performed best, as it handled categorical features more effectively than other models.

### Best Model and Results

- **Best Model**: `DecisionTreeClassifier(max_depth=4, max_features=7, min_samples_leaf=4, min_samples_split=6, random_state=42)` with **SelectKBest=6**
- **Best Model Cross-Validation Score**: 0.91  
- **ROC_AUC Score on the Test Set**: 0.92  

### Conclusions and Recommendations for the Business

- **Employee job satisfaction** is a key predictor of resignation. Continuous monitoring of employee satisfaction levels is essential.
- Employees in **higher job positions** tend to stay longer, while **newer employees** are more likely to resign.
- **Salary level** and **workload** have moderate impacts on employee attrition (ranked 4th and 5th in importance).

---

## Conclusion

This project demonstrates how machine learning models can be effectively used to predict employee satisfaction and the likelihood of employee resignation. The best-performing models for each task were:

- **Task 1 (Job Satisfaction Prediction)**: `DecisionTreeRegressor`  
- **Task 2 (Employee Resignation Prediction)**: `DecisionTreeClassifier`

The insights gained from this analysis are valuable for HR departments in proactively managing employee satisfaction and retention. By focusing on key factors such as performance ratings, salary, and job position, companies can minimize attrition and foster a more satisfied workforce.

