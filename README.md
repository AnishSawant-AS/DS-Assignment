# DS-Assignment
# Disease Prediction Model

This project is a machine learning-based disease prediction model, implemented using Python. The dataset is preprocessed, models are trained using Random Forest and Logistic Regression classifiers, and predictions are provided through a user-friendly Streamlit web app.

## Dataset

The dataset used for this model contains various medical features such as:

- Age
- BMI (Body Mass Index)
- Glucose Level
- Blood Pressure
- Cholesterol Level
- Smoking Habit
- Alcohol Consumption
- Family History of Disease

The target variable is a binary indicator representing whether the disease is present or not.

## Data Preprocessing

### Missing Values
The dataset is checked for missing values and missing entries are handled accordingly. For specific columns such as `Glucose`, `BloodPressure`, `SkinThickness`, `Insulin`, and `BMI`, missing or zero values are replaced with the median value.

### Normalization
Certain numerical features are normalized using the `MinMaxScaler` to scale the values to a range of 0 to 1, ensuring that all features contribute equally to the model's predictions.

### Correlation Analysis
A correlation matrix is generated to identify features that are highly correlated. If any feature has a correlation greater than 0.85 with another, it is considered for removal to prevent multicollinearity.

## Feature Selection

Two feature selection methods are used:

- **Chi-Square Test**: Applied to evaluate the importance of features.
- **Mutual Information**: Used to rank the features based on their information gain.

## Model Training

Two models are implemented and tuned:

1. **Logistic Regression**: A simple linear model for classification.
2. **Random Forest Classifier**: A robust ensemble model that is highly effective for classification tasks.

### Hyperparameter Tuning
Both models undergo hyperparameter tuning using `GridSearchCV` to find the best-performing set of hyperparameters. For Random Forest, a reduced hyperparameter grid is also explored for fine-tuning.

## Model Evaluation

The models are evaluated using multiple metrics:
- **Accuracy**
- **Precision**
- **Recall**
- **F1 Score**

Confusion matrices are plotted to visualize the performance of each model.

### Performance Comparison

The performance of Logistic Regression and Random Forest is compared across the various evaluation metrics. The final Random Forest model, after hyperparameter tuning, is saved as a `.pkl` file.

## Streamlit Web App

The app allows users to input medical information, such as age, BMI, glucose level, and lifestyle habits (smoking, alcohol), and get predictions on whether a disease is likely present.

### How to Run the App

1. Install the required libraries.
2. Run the Streamlit app using the following command:
   streamlit run app.py
