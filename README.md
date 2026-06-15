# Credit Card Fraud Detection using Machine Learning

This project focuses on building and evaluating multiple machine learning models to detect fraudulent credit card transactions. Utilizing an anonymized dataset, the project walks through exploratory data analysis, data splitting, model training across various classification architectures, and a deep-dive performance review using confusion matrices.

## Project Overview

Static, rule-based fraud detection frameworks struggle to capture sophisticated, evolving attack vectors. This repository addresses the problem by evaluating dynamic machine learning classifiers capable of processing complex transactional patterns. A core focus of this project is addressing the severe data imbalance common in fraud detection, where legitimate transactions vastly outnumber fraudulent ones, making standard accuracy metrics highly deceptive.

## Dataset Details

The project uses the creditcardfraud dataset from Kaggle. It contains twenty-nine numerical input variables which are features derived via PCA transformation, except for Time and Amount, and one target variable named Class. The target class uses zero for legitimate transactions and one for fraudulent transactions. The dataset is completely full with no missing or null values.

## Technical Pipeline

The notebook is built using Python 3 and relies on standard data science libraries for data manipulation, visualization, and machine learning. The dataset is split into training and testing sets using a standard split ratio to ensure a robust evaluation footprint while preserving a randomized state.

## Model Evaluation and Performance

Seven distinct machine learning algorithms were trained and evaluated based on their raw accuracy scores. The Random Forest Classifier achieved the highest score with ninety-nine point ninety-six percent accuracy. Other models evaluated in this study include K-Nearest Neighbors, Support Vector Machines, Logistic Regression, Linear Discriminant Analysis, Decision Tree Classifier, and Gaussian Naive Bayes.

## Critical Insight: The Accuracy Paradox

While the Random Forest Classifier achieved a seemingly near-perfect raw accuracy score, an in-depth analysis of the confusion matrix revealed a critical limitation. The model suffered from a high false negative rate, completely missing thirty-six out of one hundred and sixty-four actual fraud cases. These missed instances mean the system would let real fraudulent activity pass through unnoticed as legitimate transactions. In highly imbalanced datasets like fraud detection, accuracy alone is a misleading metric. The primary goal of a production-ready fraud engine must be minimizing false negatives and maximizing recall to shield institutions and consumers from direct financial loss.
