# Project Description

This project focuses on analyzing user data from a website to predict whether a user clicked on an advertisement. The dataset contains various features such as demographic information, daily internet usage, time spent on the site, and more. The project involves multiple stages, including data preprocessing, exploratory data analysis (EDA), feature engineering, model building, and evaluation.

## 1. Import Libraries and Data Loading
We begin by importing the necessary Python libraries for data analysis and machine learning. Key libraries used in this project include Pandas, NumPy, Matplotlib, Seaborn, and Scikit-Learn. The data is loaded into a Pandas DataFrame for easy manipulation.

## 2. Data Cleaning
Data cleaning is crucial to ensure the accuracy of our analysis and models. The following steps were taken to clean the data:

### Steps:
- **Changing the datatype of the "Timestamp" column**: The "Timestamp" column is converted to a proper datetime format for easier extraction of time-related features.
- **Handling missing values**: We check for missing values and handle them accordingly (e.g., filling with mean or median).
- **Removing duplicates**: Any duplicate records are dropped from the dataset.
- **Renaming the "Male" column to "Gender"**: To improve clarity, the "Male" column is renamed to "Gender" for better understanding.
- **Final Cleaning**: After addressing the missing values, duplicates, and renaming columns, the dataset is considered cleaned.

## 3. Feature Engineering
Feature engineering is essential to improve the performance of machine learning models. We extracted relevant features and checked if they would be useful for the analysis.

### Steps:
- **Extracting total hours spent by users**: The "Daily Time Spent on Site" column is used to extract the total hours spent by users.
- **Extracting month and hour**: The "Timestamp" column is used to extract only the month and hour, as the year and day do not contribute much to the analysis.

## 4. Data Preparation and Exploratory Data Analysis (EDA)
Before diving into model building, we perform EDA to gain insights into the data.

### Univariate Analysis:
We ask ourselves several questions to understand the distribution of key variables:
- What is the average daily time (in minutes) spent on the site?
- What is the average age of people visiting the site?
- What is the average yearly income of users' areas?
- Which city and country do most users come from?
- What is the most common gender of users?
- Which month and hour have the highest site usage?
- What is the average daily internet usage by users?

### Notes:
- The average daily time spent on the site is between 67 and 87 minutes.
- The average age of visitors is 30.
- The average yearly income of users' areas is between 50,000 and 70,000.
- Lisamouth and Williamsport are the cities with the most users, while France and Czech Republic have the highest number of users.
- Most visitors are female.
- February and March have the highest site usage, and 7 AM sees the most activity.
- The average daily internet usage is 180 GB.

### Bivariate Analysis:
We explore relationships between features using bivariate analysis:
- The correlation between **Daily Internet Usage** and **Daily Time Spent on Site**.
- The impact of **Gender** on **Daily Time Spent on Site**.
- The relationship between **Age** and **Daily Time Spent on Site**.
- The influence of **Area Income** on **Daily Time Spent on Site**.

### Notes:
- There is a strong positive relationship between **Daily Internet Usage** and **Daily Time Spent on Site**.
- There is a slight difference between genders in terms of time spent, with women spending more time on the site.
- Younger people tend to spend more time on the site.
- Areas with higher income have users who spend more time on the site.

### Time Series Analysis:
Time series analysis is conducted to analyze the patterns over time:
- **July** observed the highest daily time spent on the site, despite being the month with the lowest distribution. This may suggest that July was a special period, such as a free month, that encouraged more usage.

### Target Distribution:
We check the correlation of features with the target variable, "Clicked on Ad," and find that most features exhibit a good correlation with the target.

## 5. Data Splitting and Preprocessing
The dataset is split into training and testing sets to evaluate model performance. We also preprocess the data by scaling numerical features where necessary.

## 6. Model Building
The following models are used for prediction:
- Logistic Regression
- Support Vector Classifier (SVC)
- KNN Classifier
- Decision Tree Classifier
- Voting Classifier
- Random Forest Classifier
- AdaBoost Classifier
- XGBoost Classifier

### Function Definitions:
We define functions to:
- **Validate the model**: A function to validate the model's performance using cross-validation.
- **Tune the model**: A function to tune the model's hyperparameters for optimal performance.
- **Check model evaluation**: A function to evaluate the model based on key metrics like accuracy, precision, and F1 score.

## 7. Model Evaluation
The models are evaluated on the test set to identify the best performing ones.

### Evaluation Results:
- **AdaBoost**: 93% accuracy on the test set.
- **XGBoost**: 94% accuracy on the test set.
- **Random Forest**: 95% accuracy on the test set.
- **SVC**: 94% accuracy on the training set.

### Conclusion:
After evaluating the models, the **Random Forest Classifier** emerges as the best estimator, achieving an F1 score of 98% on the training set and 96% on the test set. 

### Key Insights:
- **Daily Internet Usage** and **Daily Time Spent on Site** have a strong correlation with the target variable (Clicked on Ad).
- **Age** and **Area Income** also have a good correlation with the target.

This project successfully demonstrates the use of machine learning models to predict whether a user will click on an ad based on various features, with Random Forest Classifier being the most effective model.
