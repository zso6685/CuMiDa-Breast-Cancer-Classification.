# CuMiDa-Breast-Cancer-Classification.
The project is on a Curated Micro Array dataset that aims to classify Breast cancer based on the genotype expression.
https://www.kaggle.com/datasets/brunogrisci/breast-cancer-gene-expression-cumida/data
# Business Problem / Motivation
Breast cancer is a major crisis that not only affects health of women but also negatively impacts those around them. Early detection of breast cancer is very important as this not only saves lives, it also saves resources such as time and money. Being able to accurately classify the types of breast cancer leads to being effective in treatment and efficient use of resources.
# Project Overview
The project focused on classifying breast cancer in relation to the genotype expression, with a dataset that is highly dimensional and highly imbalanced. This meant that to work with the dataset and attempt to have a reliable model we have to find effective ways to handle the curse of dimentionality. This I did by applying PCA (Principal Component Analysis) The PCA choice was 0.95 which had the most explained variance.The dataset had over 50,000+ features with 151 samples. The highest sample was 41 Basal and the lowest sample was 7 Normal. To deal with the imbalance problem, class weights were implemented on the evaluation models. The models used were Random Forest, Logistic Regression and Decision Tree all as baseline models. The best performing model was Random Forest which has a higher probability of capturing complex relations of the data better than the other models used in the baseline. 
For the metrics my focus was on macro-F1 and recall. After more advanced models like XG-boost, Logistic Regression with class weights, SVM, and Euclidean distance with the threshold 0.001 which is accurate for most medical science. The key redults after hyper-parameter tunning and cross-validation was Logistic Regression improved and became the most trust worthy model of all the models used. This is possible because after PCA the data assumes a linear relation and Weighted Logistic regression captured most of that and out-performed all the other models.
# Data
- Source: Kaggle https://www.kaggle.com/datasets/brunogrisci/breast-cancer-gene-expression-cumida/data
- Type: Tabular dataset.
- Size: (151, 54,676)
- Key features: All genotypes with high multi-collinearity therefor after PCA PC1 is a key feature having the most explained variance.
# Data Preprocessing
- The dataset was mostly clean, the genotypes could have been renamed but with over 50,000+ that would have been tedious.
- No missing values or duplicates.
- PCA 
# Exploratory Data Analysis (EDA)
-<img width="562" height="499" alt="image" src="https://github.com/user-attachments/assets/ebfd26b0-7b79-4c56-994a-56a7931290db" />
<img width="565" height="455" alt="image" src="https://github.com/user-attachments/assets/85c7a438-f272-4f2f-90e9-fd04ab5a5cd5" />

The k-means cluster was used as a EDA tool to check the distribution of the cancer types. 
The classes are highly imbalanced and for fairness I handled that using class weights, which basically forces the model to pay attention to the minority class by having the most weight to it.
# Modeling Approach
- The winning baseline model was Random Forest. This is because it can capture complex patterns in data, despite not handing the imbalance issue or dealing with the dimensionality issue, it captured most of the information but they could be a chance of possible overfitting.
- There was no need for advanced models as all the advanced models did poorly compared to Weighted Logistic Regression which was now capturing the now linear patterns assumed after PCA.
- Explain why you chose them
# Model Training
- Google colab
- Scikit learn, gridsearch_cv, pandas, numpy and more.
- Hyperparameters, I used Grid searcg_cv for my tunnning.
- For the training process data was split into train and test set. Due to fewer samples and excessive features I decided not to include a validation set. After stratified split, preprocessing was done on the train set, PCA, Eucledian approach and then models were train and then evaluated.
# Results
- Metrics chosen were Macro-F1 and recall. This is because macro-F1 has a balnced approached and forces models to also consider the less frequent classes , making them not ignred. Recall aids in otputing actual positives, and this is useful in breast cancer as we desire to know when a patient is sick and requires immediate medical attention. Thsi saves lives and resources.
- Model comparison table
- Visualizations
- <img width="509" height="470" alt="image" src="https://github.com/user-attachments/assets/e161b855-1a73-44d9-af52-2d9691e730f5" />
 <img width="509" height="470" alt="image" src="https://github.com/user-attachments/assets/0506abe6-799a-4a83-a8b9-b0058da3c991" />
 <img width="509" height="470" alt="image" src="https://github.com/user-attachments/assets/9d06638a-8092-4ed8-a3fb-b898442857af" />



# Model Interpretation
● Include model interpretation techniques such as:
The most important feature in the winning model(Logistic Regression) was PC3. 
Advanced model like XGBoost did not perform well, as we can see the model was capturing the patterns very fast and then it suddenly drops a possible overfitting.
<img width="1790" height="790" alt="image" src="https://github.com/user-attachments/assets/641b2064-d137-420c-a93d-14e05407e032" />
<img width="790" height="940" alt="image" src="https://github.com/user-attachments/assets/14b8ef20-c004-47e4-8bf9-786122d64b93" />


# Key Insights
When dealing with highly dimensional data, it is easier to go after advanced models which might not really give the best results. Something I have learnt through working on this project is that starting simple is never a bad idea. Logistic regression a linear simple model worked best as opposed to all the other models.
It is however important to note that depending on the business or entity what works best and most effective should be prioritized. In a case like breast cancer that is in need of speed, effectiveness, we should also consider interpretability as it is important for the doctors and patients to know how the model came to the final decision without jumping straight into trusting the results.
# Conclusion
- It was a quite a treat to be able to work on the dataset, to know that breast cancer could have many genetype expressions that cause certain kinds of cancer, like one example genotype could be more prevelant in one breast cancer type which could make it risky compared to its expression in other types of breast cancer. Normal does not mean cancer free but a type of breast cancer that is easier to be treated when spotted early.
# Future Work
- I would like to be able to match the genotypes expression to their actual gene name.
- Improve or add more data especially the samples.
- Check on the model performances on new data to verify that performance is the same or better.
# How to Run
- Install python or use google colab, then install the required libraries.
- Run preprocessing after stratified split to avoid the models have memory of the dataset as this causes the models to have perfect performance which could be a problem.
- Train model
- Evaluate results using confusion matrix to see what was classified correctly and which ones were misclassified.
# Repository Structure Explanation
Multiple google colabs showing changes and improvements. Copy of Demo file, SVM file is the most recent.
# Requirements
pip install -r requirements.txt

