# HR-Prediction-ML
Predic# HR Prediction ML

### Overview
This project focuses on predicting employee attrition using Machine Learning.
The dataset was first analyzed in Power BI to understand key trends and patterns.
Based on those insights we built a classification model in Python to predict
which employees are likely to leave the company.

### Dataset
- Dataset : IBM HR Analytics Employee Attrition Dataset
- Total Rows : 1470 employees
- Target Column : Attrition (Yes / No)
- Class Imbalance : 84% No Attrition, 16% Yes Attrition

## Steps Performed

### 1. Data Preprocessing
- Checked null values, data types using df.info()
- Dropped irrelevant columns like EmployeeCount, EmployeeNumber, DailyRate
- Converted all text columns to numeric using LabelEncoder

### 2. Handling Class Imbalance
- Found that dataset was highly imbalanced
- Applied SMOTE on training data to balance both classes
- This helped the model learn Attrition=Yes cases properly

### 3. Train Test Split and Scaling
- Split data into 80% training and 20% testing
- Applied StandardScaler to bring all features to same scale

### 4. Model Building

### Random Forest (First Attempt)
- Tried Random Forest Classifier with default settings
- Class 1 recall was very low at 0.29
- Model was missing most actual attrition cases
- Decided to switch to a better model

### Gradient Boosting (Default)
- Switched to Gradient Boosting as it learns from previous mistakes
- Results improved slightly compared to Random Forest

### Gradient Boosting (Tuned) - Final Model
- Tuned hyperparameters for better performance
  - n_estimators = 200
  - max_depth = 4
  - learning_rate = 0.05
- Final Accuracy : 0.81
- No overfitting issue observed

### 5. Evaluation
- Checked Accuracy Score and Classification Report
- Plotted Confusion Matrix to visualize correct and incorrect predictions

### Results
| Model | Accuracy | Class 1 Recall |
|---|---|---|
| Random Forest | 0.86 | 0.16 |
| Random Forest + SMOTE | 0.81 | 0.29 |
| Gradient Boosting | 0.78 | 0.38 |
| Gradient Boosting Tuned | 0.81 | 0.36 |

### Technologies Used
- Python
- Pandas, NumPy
- Scikit-learn
- Imbalanced-learn (SMOTE)
- Seaborn, Matplotlib

### Conclusion
Gradient Boosting with tuned hyperparameters gave the best results with
81% accuracy and balanced performance on both classes. SMOTE played a key
role in handling class imbalance which is a very common real world problem.ted employee attrition using Machine LEarning. Dataset analyzed in Power BI and ML model built in Python.
