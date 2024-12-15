# Loan Approval Prediction Machine Learning Model

## Introduction

The "Loan Approval Prediction" project is a Python-based machine learning initiative that aims to predict whether a loan application will be approved or rejected based on various applicant attributes. This documentation provides an overview of the project, covering data preprocessing, model training, and the deployment of the trained model for predictions.

## Data Preprocessing

### Loading and Cleaning Data

The project begins by uploading a dataset named "loan_approval_dataset.csv," which contains information about loan applicants. The Pandas library is used for data manipulation. The 'loan_id' column is dropped as it does not contribute to the prediction. Column names are stripped of any extra spaces for consistency.

### Feature Engineering

New features are created to simplify the dataset. A new 'Assets' column is introduced, representing the total value of residential, commercial, luxury, and bank assets. Redundant asset-related columns are then dropped to streamline the dataset.

### Handling Missing Values

The dataset is checked for missing values, ensuring data quality. Fortunately, no missing values are found. The 'education' column is cleaned by removing leading and trailing spaces for uniformity.

### Encoding Categorical Variables

Categorical variables such as 'education,' 'self_employed,' and 'loan_status' are encoded into numerical format for compatibility with machine learning algorithms. For example, 'Graduate' and 'Not Graduate' in the 'education' column are replaced with 1 and 0, respectively.

## Model Training

### Data Splitting and Scaling

The dataset is split into training and testing sets using the `train_test_split` function from scikit-learn. Standard scaling is applied to the numerical features using the `StandardScaler` to normalize the data and enhance model performance.

### Logistic Regression Model

Logistic regression is chosen as the classification algorithm due to its suitability for binary outcomes. The model is trained on the scaled training data.

### Model Evaluation

The trained model is evaluated using the test set, achieving an accuracy score of approximately 90%. This indicates that the model correctly predicts loan approval or rejection 90% of the time.

### Prediction Example

A sample loan application with specific attributes is created for prediction. The model predicts approval ('1'), indicating that the loan is likely to be approved.

## Model Deployment

To use the trained model for future predictions, it is saved using the Pickle library. Both the logistic regression model ('model.pk1') and the scaler ('scaler.pk1') are saved. These files can be loaded in other applications to make real-time loan approval predictions based on input data.
