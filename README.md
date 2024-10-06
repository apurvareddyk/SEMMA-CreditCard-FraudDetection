# Credit Card Fraud Detection Using the SEMMA Process and Random Forest

This project focuses on building a **credit card fraud detection system** using the **SEMMA** (Sample, Explore, Modify, Model, Assess) process, combined with the **Random Forest** machine learning algorithm. The goal of this project is to address the challenges posed by highly imbalanced datasets, such as the **Credit Card Fraud Detection** dataset from Kaggle, and to develop a model that can accurately detect fraudulent transactions with minimal false positives.

By following the SEMMA process, I was able to systematically approach the problem, from sampling and exploring the dataset to modifying it, building predictive models, and evaluating their performance.

[Link](https://drive.google.com/file/d/1zeBLyNILnwMAMm9JTrw3kP1sOK2FhQ07/view?usp=share_link) to dataset.

## Motivation

Financial fraud is a growing problem, with millions of dollars lost every year to fraudulent activities. Credit card fraud detection is one of the key applications of machine learning in the financial sector. Given the severity of the problem, detecting fraud accurately and efficiently is critical. However, with fraud being a rare event, the challenge lies in building a model that not only performs well on the majority class (non-fraud) but can also accurately detect the minority class (fraud) without overwhelming false positives.

## SEMMA Process Overview

The SEMMA methodology provides a structured framework for approaching data mining projects like this one. Below is a breakdown of each step as applied in this project:

### 1. Sample
The dataset consists of 284,807 transactions, with only 492 labeled as fraudulent. This represents a severe class imbalance, with fraudulent transactions accounting for just 0.17% of the dataset. In the **Sample** phase, I took a stratified sample of the data to ensure that the training set would have a representative distribution of both fraud and non-fraud transactions. This helped maintain the integrity of the data while allowing for faster iteration during model development.

### 2. Explore
In the **Explore** phase, I conducted Exploratory Data Analysis (EDA) to gain insights into the dataset:
- **Class Distribution**: A key challenge in fraud detection is the extreme class imbalance, which was visualized to show the disproportion between fraud and non-fraud cases.
- **Feature Correlations**: The features in the dataset are anonymized due to privacy concerns, but a correlation heatmap was generated to understand the relationships between these features.
- **Visualization of Key Features**: I looked at the distribution of key features like `Amount` and `Time`, comparing how they differ between fraud and non-fraud transactions. Fraudulent transactions generally had higher amounts, highlighting potential patterns that could aid in fraud detection.

### 3. Modify
Modifying the data for machine learning models is crucial, especially when dealing with imbalanced data. Here’s what was done:
- **Feature Scaling**: The dataset contains two untransformed features, `Amount` and `Time`, which were standardized using **StandardScaler** to bring them into a similar range as the PCA-transformed features.
- **Handling Class Imbalance**: Since fraudulent transactions were severely underrepresented, I used **SMOTE** (Synthetic Minority Over-sampling Technique) to generate synthetic samples for the minority class (fraud). SMOTE helps the model learn from a balanced dataset by generating artificial fraud cases, thus preventing the model from being biased toward non-fraud cases.

### 4. Model
For the **Model** phase, I experimented with three machine learning algorithms to determine which performed best on this imbalanced dataset:
- **Logistic Regression**: A widely-used model for binary classification.
- **Decision Tree**: A non-linear model that can capture complex relationships in the data.
- **Random Forest**: An ensemble learning method that builds multiple decision trees and averages their predictions, reducing overfitting and improving accuracy.

Each model was trained on the balanced dataset created using SMOTE and evaluated based on several metrics including **accuracy**, **precision**, **recall**, **F1-score**, and **ROC-AUC score**. The **Random Forest** model emerged as the best performer, achieving a **99% accuracy** and an **ROC-AUC score of 0.9994**, indicating that it could almost perfectly distinguish between fraudulent and non-fraudulent transactions.

### 5. Assess
The **Assess** phase involved evaluating the final model (Random Forest) in detail:
- **Confusion Matrix**: The confusion matrix showed a high number of true positives and true negatives, with minimal false positives and false negatives. This means the model was excellent at correctly identifying both fraudulent and non-fraudulent transactions.
- **Classification Report**: The classification report provided high precision and recall scores for both classes. The F1-score, a harmonic mean of precision and recall, was also near perfect, ensuring that the model was balanced in its ability to identify fraud without creating too many false alarms.
- **ROC Curve and AUC**: The **ROC Curve** showed a near-perfect trade-off between true positives and false positives, with an **AUC score of 0.9994**, indicating the model's excellent performance in separating the classes.
- **Feature Importance**: An analysis of the feature importance in the Random Forest model revealed which of the anonymized features had the most significant influence on detecting fraud. Understanding feature importance is critical for model interpretability and future improvements.

## Challenges and Solutions

- **Class Imbalance**: One of the major challenges in this project was the extreme class imbalance. Fraudulent transactions make up less than 0.2% of the dataset. To counter this, I used **SMOTE**, which helped balance the classes and significantly improve the model's performance.
- **Feature Anonymization**: Since the features in the dataset were anonymized, it was challenging to interpret their real-world meaning. However, by focusing on feature importance and patterns within the data, I was able to create a model that still provided high predictive power despite this limitation.

## Key Metrics and Results

- **Accuracy**: 99%
- **Precision**: 100% (for fraud class)
- **Recall**: 99%
- **F1-Score**: 99%
- **ROC-AUC Score**: 0.9994

The **Random Forest** model demonstrated exceptional performance, especially in detecting fraudulent transactions while minimizing false positives. This is crucial in a real-world setting where the cost of misclassifying a legitimate transaction as fraud could lead to user frustration.

## Links

- [Medium Article: Detecting Credit Card Fraud Using the SEMMA Process and Random Forest](https://medium.com/@apurva.karne/detecting-credit-card-fraud-using-the-semma-process-and-random-forest-d3890d014030)
- [Colab Notebook](https://colab.research.google.com/drive/1joqZ4hcGgfqHXcy1cFCb83ICA7E1QSU5#scrollTo=eHV4QyDjHM0i)

## Conclusion

Through the SEMMA process, I successfully developed a powerful credit card fraud detection system using Random Forest. The model achieved high precision and recall, making it an effective solution for detecting fraud in real-world applications. This project demonstrates the importance of a structured approach to data mining, especially when dealing with imbalanced datasets. By applying methods like SMOTE and leveraging robust models like Random Forest, I was able to build a solution that meets the demands of modern fraud detection.

For more details on the process and code implementation, check out the project’s [Medium article](https://medium.com/@apurva.karne/detecting-credit-card-fraud-using-the-semma-process-and-random-forest-d3890d014030) and the [Colab Notebook](https://colab.research.google.com/drive/1joqZ4hcGgfqHXcy1cFCb83ICA7E1QSU5#scrollTo=eHV4QyDjHM0i).

## About the Author

I am **Apurva Karne**, a Master’s student in Software Engineering with a specialization in Data Science. I am passionate about building data-driven solutions for real-world challenges, particularly in the field of fraud detection. Follow my work on [Medium](https://medium.com/@apurva-karne) for more articles on machine learning, data science methodologies, and cutting-edge technology.
