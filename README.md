# Credit_Risk_Analysis

## Overview
The purpose of this analysis is to utilize supervised machine learning algorithms to predict credit risk. Data was sourced from LendingClub. The dataset was for over 100,000 applications from Q1 2019. This analysis was conducted on the ~69,000 issued loans. Over 80 [variables](https://help.lendingclub.com/hc/en-us/articles/215488038-What-do-the-different-Note-statuses-mean-) were used as features in the machine learning models. The LendingClub dataset has an unbalanced classification problem, since high risk loans are far outnumbered by low risk loans. Because of this, the models used throughout this analysis aim to accommodate that limitation. Algorithms used include: RandomOverSampler, SMOTE, ClusterCentroids (for Undersampling), SMOTEENN, Balanced Random Forests, and Easy Ensemble Classifier. 

Required dependencies: Pandas, Sci-kit learn, imbalanced learn, numpy.

## Results
### Preview of the Data
The following is a preview of the training and testing data after preprocessing for all models in this analysis. Stratification was used due to the imbalance between classes of the target variable, loan status.

![image](https://user-images.githubusercontent.com/93338132/165002563-3a67a52f-043a-4492-a876-2b233c996e53.png)

### Results Summary 

The following table summarizes results by model. Precision and Recall (sensitivity) are shown for high risk loan identification, as that is what this model is ultimately trying to identify. Detailed results for each model are in following sections.

| Model | Balanced Accuracy Score | Precision (for high risk) | Recall (for high risk)
| --- | --- | --- | --- |
| Random Oversampling | 64.56% | 0.01 | 0.61 |
| SMOTE Oversampling | 62.34% | 0.01 | 0.61 |
| Cluster Centroid Undersampling | 52.19% | 0.01 | 0.59 |
| SMOTEENN | 63.96% | 0.01 | 0.70 |
| Balanced Random Forest  | 78.78% | 0.04 | 0.67 |
| Easy Ensemble | 92.54% | 0.07 | 0.91 |

### Random Oversampling 
![image](https://user-images.githubusercontent.com/93338132/165003228-52606587-ad5a-43c7-a633-607b836d0c8f.png)

### SMOTE Oversampling
![image](https://user-images.githubusercontent.com/93338132/165003247-88e8347b-5fac-49af-8aaa-4dfa349e89c3.png)

### Cluster Centroid Undersampling
![image](https://user-images.githubusercontent.com/93338132/165003281-1688bd95-eb4a-4c0a-8ae7-79ebe5b6c993.png)

### SMOTEEN 
![image](https://user-images.githubusercontent.com/93338132/165003311-d874aa11-a68b-4fe2-b357-4416c1f38328.png)

### Balanced Random Forest
![image](https://user-images.githubusercontent.com/93338132/165003378-1147f63a-ef8b-4860-88e3-2986862ae682.png)

### Easy Ensemble 
![image](https://user-images.githubusercontent.com/93338132/165003414-ced51d44-25c4-450b-a0a1-e063e10d9a17.png)


| Balanced Random Forest  | 78.78% | 0.04 | 0.67 |
