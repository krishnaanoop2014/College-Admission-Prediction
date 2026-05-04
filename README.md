College Admission Prediction
Project Overview
This project builds a predictive model to estimate the "Chance of Admit" for graduate school applicants. It uses parameters such as GRE scores, TOEFL scores, University Rating, SOP (Statement of Purpose) strength, LOR (Letter of Recommendation) strength, CGPA, and Research experience.

Workflow
Exploratory Data Analysis (EDA):

Loads a dataset of 500 entries and 9 columns.

Renames columns for easier access (e.g., Chance of Admit to Probability).

Generates histograms to visualize the distribution of academic scores and university ratings.

Data Cleaning:

Drops the Serial No. column as it is an identifier with no predictive value.

Checks for and handles missing values.

Model Selection:

Compares multiple regression algorithms using GridSearchCV:

Linear Regression

Lasso Regression

Support Vector Regression (SVR)

Decision Tree

Random Forest

K-Nearest Neighbors (KNN)

Result: Linear Regression was selected as it achieved the highest accuracy (approx. 81.08% via cross-validation).

Training & Testing:

Splits data into an 80/20 train-test ratio.

Final model evaluation on the test set achieves an R² score of approximately 0.82.

How to Use
To predict the admission probability, use the model.predict() method with a list of features in this specific order:
[GRE, TOEFL, University Rating, SOP, LOR, CGPA, Research]

Example Snippet:

Python
Predict for a student with GRE 337 and CGPA 9.65
prediction = model.predict([[337, 118, 4, 4.5, 4.5, 9.65, 0]])
print(f"Chance of Admit: {prediction[0]*100}%")
