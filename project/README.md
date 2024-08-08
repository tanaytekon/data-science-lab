# AIN212 Data Science Project

## Contributors

- **Tanay Tekön** - Hacettepe University - Artificial Intelligence Engineering - 2200765013
- **Harun Harman** - Hacettepe University - Artificial Intelligence Engineering - 2200765008

## Project Overview

This project is part of the AIN212 Data Science class. The goal of this project is to predict the risk level of COVID-19 patients using a comprehensive dataset provided by the Mexican government. This project includes data preprocessing, handling class imbalance, feature engineering, applying machine learning models, performing dimensionality reduction and clustering, and detailed evaluation of applied machine learning models.

## Dataset and Preprocessing

The dataset used in this project consists of over one million records with 21 unique features. It includes anonymized patient-related information such as pre-existing conditions, demographics, and outcomes.

### Key Preprocessing Steps:

- **Handling Missing Data:** Missing values were dropped or derived from other features by carefully investigating the feature values and their meanings.
- **Feature Engineering:** Created new features, such as a binary "DEAD" indicator derived from the "DATE_DIED" column, which simplified modeling by categorizing patients based on survival status.
- **Data Cleaning:** Categorical features, such as "INTUBED" and "PATIENT_TYPE," were cleaned and encoded to make them suitable for machine learning algorithms.
- **Class Imbalance:** The dataset exhibited a significant class imbalance in the target variable. This was handled using class-weight adjustments.

## Exploratory Data Analysis (EDA)

EDA was performed to gain insights into the dataset, visualize feature distributions, and understand relationships between different variables. Visualizations were created using Seaborn and Matplotlib.

- **Feature Distributions:** Distributions of the target variable and features investigated.
- **Correlation Heatmap:** Correlations between the features were investigated through correlation heatmap.

## Clustering Analysis and PCA

Clustering analysis and Principal Component Analysis (PCA) were applied to explore the dataset further:

- **Clustering Analysis:** An unsupervised learning technique, **Agglomerative Clustering** were applied to identify natural groupings within the data. Number of clusters determined as 4, by using elbow method. This analysis provided additional insights into the underlying patterns and helped in understanding patient segments.
- **PCA:** PCA was applied to reduce the dimensionality of the dataset, making it easier to visualize and analyze. Dimensionality was reduced the 3D for visualization.
- **Visualization of Clusters:** Clusters were visualized on dimensionally reduced data. The distribution and formation of the clusters on each feature with the target variable were also shown. 

## Modeling and Evaluation

Two models were employed in this project: **Decision Tree** and **Logistic Regression**.

### Handling Class Imbalance:

The class imbalance issue was addressed by:

- **Class Weights:** Adjusting the class weights in both Decision Tree and Logistic Regression models to give higher importance to the minority class. Class weights were adjusted inversely proportional to class frequencies in the input data

### Key Metrics Considered:

- **Accuracy:** To measure the overall correctness of the model's predictions.
- **Recall, Specificity:** To evaluate the percentage of correct predictions among the data that have the same predicted class.
- **Precision, False Positive Rate:** To evaluate the percentage of correct predictions among the data that have the same ground truth class.
- **ROC-AUC and Precision-Recall AUC Scores:** To assess the model's ability to distinguish between classes.
- **Confusion Matrix:** Confusion matrices of both models, before and after hyperparameter tuning, were visually investigated, and the results of the above evaluation metrics were discussed in detail.


## Results Interpretation

The results from the models were interpreted and discussed in detail in the notebook using the key metrics above. It was concluded that the Logistic Regression model outperformed the Decision Tree model for this dataset. The summarized results can be seen in the table below:

Models | Accuracy | Precision | False Positive Rate | Specificity | Recall | ROC-AUC | Precision-Recall AUC
--- | --- | --- | --- |--- |--- |--- |---
**Logistic Regression** | 0.90 | 0.41 | 0.10 | 0.90 | **0.91** | **0.96** | **0.68**
**Decision Tree** | **0.91** | **0.43** | **0.07** | **0.93** | 0.69 | 0.81 | 0.53