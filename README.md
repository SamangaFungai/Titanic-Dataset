# Titanic-Dataset
# Titanic Survival Prediction using Machine Learning

## Project Overview

This project explores the famous Titanic dataset and builds machine learning models to predict passenger survival.

The project covers the complete machine learning workflow:

* Data Cleaning
* Exploratory Data Analysis (EDA)
* Feature Engineering
* Data Preprocessing
* Logistic Regression
* Random Forest Classification
* Model Evaluation and Interpretation

The goal of this project was not only to build a predictive model, but also to understand the reasoning behind each machine learning step.


# Dataset Information

The dataset contains information about Titanic passengers such as:

* Passenger Class (`Pclass`)
* Sex
* Age
* Fare
* Family relationships (`sibsp`, `Parch`)
* Embarkation Port (`Embarked`)
* Survival Status (`survived`)

Target Variable:

 survived`
[`0` ]= Did not survive
[`1`] = Survived

# Project Workflow

## 1. Data Cleaning

The dataset was cleaned by:

* Removing unnecessary columns
* Handling missing values
* Fixing column naming issues
* Encoding categorical variables
* Preparing the data for machine learning

### Key Cleaning Step

Unnecessary (`zero.`) columns were removed because they contained no useful information and could negatively affect model performance.

## 2. Exploratory Data Analysis (EDA)

EDA was performed to understand patterns and relationships within the dataset.

### Important Findings

* Female passengers had a higher survival rate than males.
* First-class passengers had better survival chances.
* Higher ticket fares were associated with higher survival probability.
* Family structure appeared to influence survival.

### Visualizations Used

* Bar plots
* Histograms
* Boxplots
* Correlation heatmaps

These visualizations helped identify important patterns before building machine learning models.

## 3. Feature Engineering

Additional features were created to improve model performance.

### Family Size Feature

FamilySize = sibsp + Parch + 1

This feature helped capture whether passengers were traveling alone or with family.

### IsAlone Feature

IsAlone = (FamilySize == 1)

This feature helped identify solo travelers.

# Machine Learning Models

## Logistic Regression

Logistic Regression was used as the baseline model because:

* It performs well on binary classification problems.
* It is simple and interpretable.
* It provides a strong starting point for comparison.

### Initial Results

* Accuracy: ~76.7%

The model performed reasonably well but struggled to correctly identify survivors.

## Random Forest Classifier

A Random Forest model was later introduced to capture more complex relationships within the data.

### Why Random Forest?

* Handles non-linear relationships better.
* Reduces overfitting using multiple decision trees.
* Often performs well on structured/tabular datasets.

### Tuned Parameters
RandomForestClassifier(
    n_estimators=200,
    max_depth=5,
    class_weight='balanced',
    random_state=42
)
# Model Evaluation

The models were evaluated using:

* Accuracy
* Confusion Matrix
* Precision
* Recall
* Classification Report

## Important Insight

The project demonstrated that accuracy alone is not always the best metric.

After balancing the Random Forest model:

* Recall for survivors improved significantly.
* More survivors were correctly identified.
* Overall accuracy decreased slightly, showing the trade-off between precision and recall.

This reflects a real-world machine learning challenge where improving one metric can negatively affect another.

# Final Results

## Balanced Random Forest

* Accuracy: 75%
* Improved survivor recall
* Better detection of positive cases

Confusion Matrix:

```text
[147  42]
[ 21  52]
```

This model was preferred because it identified significantly more survivors compared to earlier models.

# Technologies Used

* Python
* Pandas
* NumPy
* Matplotlib
* Seaborn
* Scikit-learn
* Jupyter Notebook

# What I Learned

Through this project, I learned:

* How to clean real-world datasets
* The importance of EDA
* Feature engineering techniques
* How machine learning models make predictions
* Model evaluation and interpretation
* Trade-offs between accuracy, precision, and recall
* The importance of understanding data rather than only training models

# Future Improvements

Possible future improvements include:

* Hyperparameter tuning using GridSearchCV
* Cross-validation
* XGBoost implementation
* Advanced feature engineering
* Model deployment using Flask or Streamlit

# Conclusion

This project demonstrates a complete end-to-end machine learning workflow using the Titanic dataset.

The focus of the project was not only achieving good model performance, but also understanding the reasoning behind every step in the machine learning process.
