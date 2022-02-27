# Credit Risk Analysis

## Overview of Project

In this project, Python was used to build and evaluate several machine learning models to predict credit risk.
The following procedure was adopted:

* Oversample the data using the RandomOverSampler and SMOTE algorithms.
* Undersample the data using the ClusterCentroids algorithm.
* Use a combinatorial approach of over- and undersampling using the SMOTEENN algorithm.
* Compare two machine learning models that reduce bias, BalancedRandomForestClassifier and EasyEnsembleClassifier.

Evaluate the performance of these models and make a recommendation on whether they should be used to predict the credit risk of a customer.

## Resources

* Data Source: Data Source: LoanStats_2019Q1.csv
* Software: Python 3.7.9, Anaconda Navigator 1.9.12, Conda 4.8.4, Jupyter Notebook 6.0.3


## Results (Balanced Accuracy Scores, Confusion Matrixes and Imbalanced Classification Reports)

### RandomOverSampler model

<p align="center"> <img src=https://user-images.githubusercontent.com/92001105/155902018-3ea7e943-5c58-4bc7-99b2-502b710e3d35.png> </p>

<p align="center"> <img src= https://user-images.githubusercontent.com/92001105/155902025-4297dc01-300f-4acc-b98c-41e3e26adb2b.png> </p>

<p align="center"> <img src = https://user-images.githubusercontent.com/92001105/155902032-57ae9c04-dc2b-4560-ade1-c4137dae9928.png> </p>

The balanced accuracy score is 62%.
The high_risk precision is about 1% only with 60% sensitivity which makes a F1 of 2% only.
Due to the high number of the low_risk population, its precision is almost 100% with a sensitivity of 65%.

### SMOTE model

<p align="center"> <img src = https://user-images.githubusercontent.com/92001105/155902299-28836f4f-9b06-4cd6-a45f-3711768f0b29.png> </p>

<p align="center"> <img src= https://user-images.githubusercontent.com/92001105/155902304-89ccca6d-8422-4d49-8bc5-31848ac4d1e0.png> </p>

<p align="center"> <img src = https://user-images.githubusercontent.com/92001105/155902312-1f95f3b0-2789-46e2-bf30-b6bf14f83514.png> </p>

The balanced accuracy score is 65%.
The high_risk precision is about 1% only with 64% sensitivity which makes a F1 of 2% only.
Due to the high number of the low_risk population, its precision is almost 100% with a sensitivity of 66%.

### ClusterCentroids model

<p align="center"> <img src = https://user-images.githubusercontent.com/92001105/155903120-55a2a1ca-958f-4f9c-835d-b4d81a1711ff.png> </p>

<p align="center"> <img src = https://user-images.githubusercontent.com/92001105/155903124-15f89dfe-b4ea-4ea3-977d-40beb80ba9b6.png> </p>

<p align="center"> <img src = https://user-images.githubusercontent.com/92001105/155903128-c3bca172-bc79-46b9-afc6-33a32f6f2925.png> </p>

Here the balanced accuracy score is only 51%.
The high_risk precision is still 1% only with 59% sensitivity which makes a F1 of 1%.
Due to the high number of false positives, the low_risk sensitivity is only 43%.

### SMOTEENN model

<p align="center"> <img src = https://user-images.githubusercontent.com/92001105/155903552-458e6041-bd49-40de-b616-e6d07c029c52.png> </p>

<p align="center"> <img src = https://user-images.githubusercontent.com/92001105/155903558-2699e1fc-c993-47b4-bd9e-2d3f1885bb13.png> </p>

<p align="center"> <img src = https://user-images.githubusercontent.com/92001105/155903562-5b31c0a7-9145-4478-9ef7-b43eebc7fe23.png> </p>

The balanced accuracy score is about 64%.
The high_risk precision is still 1% only with 70% sensitivity which makes a F1 of only 2%.
Due to the high number of false positives, the low_risk sensitivity is 57%.

### BalancedRandomForestClassifier model

<p align="center"> <img src = https://user-images.githubusercontent.com/92001105/155903738-4ea55c7e-74d4-4432-8ec3-195060d5c4c5.png> </p>

<p align="center"> <img src = https://user-images.githubusercontent.com/92001105/155903743-18a56e65-4fed-47fa-89eb-09f7eb8afd93.png> </p>

<p align="center"> <img src = https://user-images.githubusercontent.com/92001105/155903749-7dc7ce1a-35b2-4971-b5b0-2f6d2bd073e0.png> </p>

The balanced accuracy score improved to about 79%.
The high_risk precision is still low at 4% only with 67% sensitivity which makes a F1 of only 7%.
Due to a lower number of false positives, the low_risk sensitivity is now 91% with 100% presicion.

### EasyEnsembleClassifier model

<p align="center"> <img src = https://user-images.githubusercontent.com/92001105/155903932-d9569962-1419-47df-a7fc-76680d0eeffa.png> </p>

<p align="center"> <img src = https://user-images.githubusercontent.com/92001105/155903944-39779fed-df8f-4955-833b-6cb8d88b5537.png> </p>

<p align="center"> <img src = https://user-images.githubusercontent.com/92001105/155903948-747a3384-9bb0-4bb4-a76b-cd322233dd9f.png> </p>

Now, the balanced accuracy score is high to about 93%.
The high_risk precision is still low at 7% only with 91% sensitivity which makes a F1 of only 14%.
Due to a lower number of false positives, the low_risk sensitivity is now 94% with 100% precision.

## Summary

The models used to perform the credit risk analysis show weak precision in determining if a credit risk is high.
The Ensemble models brought a lot more improvement on the sensitivity of the high risk credits.
The EasyEnsembleClassifier model shows a recall of 92% so it detects almost all high risk credit. On the other hand, with a low precision, a lot of low risk credit are still falsely detected as high risk which would penalize the bank's credit strategy and negatively impact profitability by missing out on these business opportunities.
For those reasons I would not recommend the bank to use any of these models to predict credit risk.
