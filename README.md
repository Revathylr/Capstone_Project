# Capstone_Project_Predictive_maintenance
PREDICTIVE MAINTENANCE OF MACHINES AND INDUSTRIAL EQUIPMENT



The primary objective of this project is to develop a predictive maintenance system using machine learning techniques that can accurately anticipate potential failures or maintenance needs of industrial machinery.

By leveraging sensor data—specifically Torque [Nm], Rotational Speed [rpm], Process Temperature [K], Air Temperature [K], and Tool Wear [min]

The model aims to:

1.Detect early signs of equipment degradation or malfunction.

2.Classify the operational state of the machine into risk categories.

3.Minimize unplanned downtime and maintenance costs

4.Enable industries to shift from reactive/scheduled maintenance to condition-based and predictive maintenance strategies.

5.Improve overall equipment efficiency, safety, and reliability.

The project will involve data preprocessing, exploratory data analysis, feature engineering, model development (using classification algorithms), and performance evaluation to deliver a robust predictive maintenance solution.



⚙️ Machine Learning Pipeline Overview (Logistic Regression)


1. 🧼 Preprocessing Stage (preprocessor)
Handled by a ColumnTransformer, which applies different preprocessing steps to numerical and categorical features:

🧮 Numerical Features
Imputation: Missing values are filled using the mean.
Scaling: Standardized using StandardScaler (zero mean, unit variance).

🔤 Categorical Features
Imputation: Missing values are filled with the most frequent value.
Encoding: Transformed using OneHotEncoder with handle_unknown='ignore' to support unseen categories during inference.

2. 🧠 Classification Stage (classifier)
Uses a Logistic Regression model:

Linear classifier, interpretable and efficient.
Regularization support: L1 (Lasso) and L2 (Ridge).
Hyperparameters used:
penalty: Type of regularization (l1, l2)
C: Inverse of regularization strength
max_iter: Maximum optimization iterations


3. 🔍 Model Training & Hyperparameter Tuning
Training is done using GridSearchCV, which:

Wraps the entire pipeline
Performs cross-validated grid search using StratifiedKFold
Selects the best hyperparameters based on accuracy
🔧 Hyperparameters Tuned:
Parameter	Description
classifier__penalty	Type of regularization (l1, l2)
classifier__C	Regularization strength (0.01 to 100)
classifier__max_iter	Maximum iterations for solver


4. 💾 Model Saving & Deployment
The best model and preprocessing pipeline are saved using joblib:
joblib.dump(grid_search.best_estimator_, "logreg_pipeline.pkl")





