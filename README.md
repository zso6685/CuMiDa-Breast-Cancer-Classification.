# CuMiDa-Breast-Cancer-Classification.
The project is on a Curated Micro Array dataset that aims to classify Breast cancer based on the genotype expression.
https://www.kaggle.com/datasets/brunogrisci/breast-cancer-gene-expression-cumida/data
# Business Problem / Motivation
Breast cancer is a major crisis that not only affects health of women but also negatively impacts those around them. Early detection of breast cancer is very important as this not only saves lives, it also saves resources such as time and money. Being able to accurately classify the types of breast cancer leads to being effective in treatment and efficient use of resources.
# Project Overview
Short summary of goal, approach, and key results
The project focused on classifying breast cancer in relation to the genotype expression, with a dataset that is highly dimensional and highly imbalanced. To deal with these issue I applied PCA to deal with the dimensionality issue. The dataset had over 50,000+ features with 151 samples. The highest sample was 41 Basal and the lowest sample was 7 Normal. To deal with the imbalance problem, class weights were implemented on the evaluation models. The models used were Random Forest, Logistic Regression and Decision Tree for the baseline. The best performing model was Random Forest which has a higher probability of capturing complex relations of the data better than the other models used in the baseline. For further analysis, and to deal with the problem at hand, PCA was implemented to aid in the dimensionality reduction and the choice was 0.95% which had the highest explained variance. 
For the metrics my focus was on macro-F1 and recall. After more advanced models like XG-boost, Logistic Regression with class weights, SVM, and Euclidean distance with the threshold 
# Data
- Source: Kaggle https://www.kaggle.com/datasets/brunogrisci/breast-cancer-gene-expression-cumida/data
- Type: Tabular dataset.
- Size: (151, 54,676)
- Key features: All genotypes with high multi-collinearity therefor after PCA PC1 is a key feature having the most explained variance.
# Data Preprocessing
- Cleaning steps
- Handling missing values
- Feature engineering
# Exploratory Data Analysis (EDA)

