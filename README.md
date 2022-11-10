# **Amazon Vine Analysis**


## **Overview**
Fast Lending, is a peer to peer lending services company that wants to use machine learning to predict the credit risk of loan applicants. Credit risk is an inherently unbalanced classification problem, as good loans easily outnumber risky loans. Therefore, this project will explore, implement and evaluate the peformance of multiple resampling and classification models to determine if any of them can be used to predict credit risk.

<br>

## **Results**
Four resampling models and two classification models were explored in this project. All resampling models were paired with a logistic regression model to obtain their results. 

Resampling Models:
- Naive Random Oversampling
- SMOTE Oversampling
- Cluster Centroid Undersampling
- SMOTEENN Sampling

Classification Models:
- Balanced Random Forest Classification
- Easy Ensemble AdaBoost Classification

Below is a breakdown and an interpretation of the balanced accuracy score, the precision score and the recall score for each machine learning model. For reference, low_risk or the number one in the confusion matrix refers to good loan applications and high_risk or the number zero in the confusion matrix refers to bad loan applications.

<br>

### **Naive Random Oversampling**

- The accuracy score is 0.65 which tells us that the model is mediocre at correctly classifying applications.
- The precision is high, nearly 100%, for the majority class but extremely low for the minority class. Only 1% of bad applications were correctly identified by the model. 
- The recall or sensitivy is mediocre with a score of 0.71 for high risk applications and a score of 0.58 for low risk applications. This means that a moderate number of positive samples for either class have not been found. 

<br>
<p align="center">
    <img src="images/Naive Random Oversampling Results.PNG">
    Figure 1 (Naive Random Oversampling Results)
</p>
<br>

### **SMOTE Oversampling**

- The accuracy score is 0.66 which tells us that the model is mediocre at correctly classifying applications.
- The precision is high, nearly 100%, for the majority class but extremely low for the minority class. Only 1% of bad applications were correctly identified by the model. 
- The recall or sensitivy is mediocre with a score of 0.63 for high risk applications and a score of 0.68 for low risk applications. This means that a moderate number of positive samples for either class have not been found. 

<br>
<p align="center">
    <img src="images/SMOTE Oversampling Results.PNG"><br>
    Figure 2 (SMOTE Oversampling Results)<br>
</p>
<br>

### **Cluster Centroid Undersampling**

- The accuracy score is 0.55 which tells us that the model is not good at correctly classifying applications.
- The precision is high, nearly 100%, for the majority class but extremely low for the minority class. Only 1% of bad applications were correctly identified by the model. 
- The recall or sensitivy is mediocre for high risk applications with a score of 0.69 and not good for low risk applications with a score of 0.40. This means that a moderate number of positive samples for high risk applications have not been found and a high number of positive samples for low risk applications have not been found.

<br>
<p align="center">
    <img src="images/Cluster Centroid Undersampling Results.PNG"><br>
    Figure 3 (Cluster Centroid Undersampling Results)<br>
</p>
<br>

### **SMOTEENN Sampling**

- The accuracy score is 0.64 which tells us that the model is mediocre at correctly classifying applications.
- The precision is high, nearly 100%, for the majority class but extremely low for the minority class. Only 1% of bad applications were correctly identified by the model. 
- The recall or sensitivy is mediocre with a score of 0.68 for high risk applications and a score of 0.59 for low risk applications. This means that a moderate number of positive samples for either class have not been found. 

<br>
<p align="center">
    <img src="images/SMOTEENN Sampling Results.PNG"><br>
    Figure 4 (SMOTEENN Sampling Results)<br>
</p>
<br>

### **Balanced Random Forest**

- The accuracy score is 0.79 which tells us that the model is good at correctly classifying applications. However, this is a misleading score as the dataset is unbalanced. The pronounced imbalance between the two classes is likely causing the machine learning model to be biased toward the majority class (low risk applicants).
- The precision is high, nearly 100%, for the majority class but extremely low for the minority class. Only 3% of bad applications were correctly identified by the model. 
- The recall or sensitivy is good with a score of 0.70 for high risk applications and a score of 0.87 for low risk applications. This means that a small number of positive samples for either class have not been found. 

<br>
<p align="center">
    <img src="images/Balanced Random Forest Results.PNG"><br>
    Figure 5 (Balanced Random Forest Results)<br>
</p>
<br>

### **Easy Ensemble AdaBoost**

- The accuracy score is 0.93 which tells us that the model is very good at correctly classifying applications. However, this is a misleading score as the dataset is unbalanced. The pronounced imbalance between the two classes is likely causing the machine learning model to be biased toward the majority class (low risk applicants).
- The precision is high, nearly 100%, for the majority class but extremely low for the minority class. Only 9% of bad applications were correctly identified by the model. 
- The recall or sensitivy is very good with a score of 0.92 for high risk applications and a score of 0.94 for low risk applications. This means that a very small number of positive samples for either class have not been found. 

<br>
<p align="center">
    <img src="images/Easy Ensemble AdaBoost Results.PNG"><br>
    Figure 6 (Easy Ensemble AdaBoost Results)<br>
</p>
<br>

## **Summary**
- None of the models were able to to reliably and correctly idenify high risk loan applicants. 
- None of the resampling methods outperformed the standard sampling used in the classifying models tested. 
- The Easy Ensemble AdaBoost classification model  outperformed the Balanced Random Forest model in all measured categories. However, both were still misleading in their accuracy as both had too many false positives for high risk loan applicants. 

In conclusion, none of the tested models would be recommended for use in predicting the credit risk of loan applicants. While some of the models, such as the Easy Ensemble AdaBoost, provide some value in being able to predict good applicants, they do not provide enough value to warrant usage as they cannot reliably distinguish between good and bad applicants. 

Further exploration of combinations between resampling and classification models is recommended. In particular, exploring different resampling  methods with the Easy Ensemble AdaBoost classification model would be a good place to start as this classification model obtained the highest precision in identifying high risk loan applicants. Providing this model with a more balanced data set through resampling could potentially improve its performance.