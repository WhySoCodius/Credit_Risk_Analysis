# Credit_Risk_Analysis

## Purpose
 
The objective of this study is to analyse and forecast the level of risk associated with loans granted by Lending Club using various supervised machine learning techniques.

## Resources 
### Data Source
[LoanStats_2019Q1](/LoanStats_2019Q1.csv) is used to forecast the risk associated.

### Softwares:
![Python](https://img.shields.io/badge/python-3670A0?style=for-the-badge&logo=python&logoColor=ffdd54)
![Pandas](https://img.shields.io/badge/pandas-%23150458.svg?style=for-the-badge&logo=pandas&logoColor=white)
![NumPy](https://img.shields.io/badge/numpy-%23013243.svg?style=for-the-badge&logo=numpy&logoColor=white)
![scikit-learn](https://img.shields.io/badge/scikit--learn-%23F7931E.svg?style=for-the-badge&logo=scikit-learn&logoColor=white)
![SciPy](https://img.shields.io/badge/SciPy-%230C55A5.svg?style=for-the-badge&logo=scipy&logoColor=%white)
![Jupyter Notebook](https://img.shields.io/badge/jupyter-%23FA0F00.svg?style=for-the-badge&logo=jupyter&logoColor=white)

## Results

**### Oversampling: Native Random Oversampling ---------------------------------------------- I**

Random oversampling involves adding instances of the minority class to the training set at random until the majority and minority classes are balanced.

- Balanced Accuracy Score : 63.46% 
    - High-Risk Precision : 0.01
    - High-Risk Recall : 0.74
- [Confusion Matrix](/Resources/CM_Native_Random_Oversampling.png)
- Classification Report :
![Native_Random_Oversampling](/Resources/CR_Native_Random_Oversampling.png)

**### Oversampling: SMOTE ------------------------------------------------------------------- II**

A method of oversampling used to deal with uneven datasets is called Synthetic Minority Oversampling Technique (SMOTE).

- Balanced Accuracy Score : 65.83%
    - High-Risk Precision : 0.01
    - High-Risk Recall : 0.63
- [Confusion Matrix](/Resources/CM_Oversampling_SMOTE.png)
- Classification Report :
![Oversampling_SMOTE](/Resources/CR_Oversampling_SMOTE.png)

**### Undersampling: Random Undersampling --------------------------------------------------- III**

Random undersampling is used when instances from the majority class are randomly chosen and eliminated until the size of the majority class is decreased (typically to the size of the minority class).

- Balanced Accuracy Score : 54.43%
    - High-Risk Precision : 0.01
    - High-Risk Recall : 0.74
- [Confusion Matrix](/Resources/CM_Undersampling.png)
- Classification Report :
![Undersampling](/Resources/CR_Undersampling.png)

**### Combination Sampling: SMOTEENN -------------------------------------------------------- IV**

SMOTE and Edited Nearest Neighbor (ENN) algorithms are combined to create SMOTEENN. There are two steps to this process:
1. SMOTE should oversample the minority class. 
2. Utilize an undersampling approach to clean the generated data. A data point is dropped if its two closest neighbours come from two different classes.

    - Balanced Accuracy Score : 65.77%
        - High-Risk Precision : 0.01
        - High-Risk Recall : 0.74
    - [Confusion Matrix](/Resources/CM_SMOTEENN.png)
    - Classification Report :
![SMOTEENN](/Resources/CR_SMOTEENN.png)

**### Balanced Random Forest Classifier ----------------------------------------------------- V**

An ensemble method called a balanced random forest uses random undersampling to create balance.

- Balanced Accuracy Score : 78.77%
    - High-Risk Precision : 0.04
    - High-Risk Recall : 0.67
- [Confusion Matrix](/Resources/CM_BalancedRandomForestClassifier.png)
- Classification Report :
![BalancedRandomForestClassifier](/Resources/CR_BalancedRandomForestClassifier.png)

**### Easy Ensemble AdaBoost Classifier ----------------------------------------------------- VI**

EasyEnsemble is a bag of balanced, boosted students. Random under-sampling is used to achieve the balancing.

- Balanced Accuracy Score : 92.54%
    - High-Risk Precision : 0.07
    - High-Risk Recall : 0.91
- [Confusion Matrix](/Resources/CM_EasyEnsemble.png)
- Classification Report :
![EasyEnsemble](/Resources/CR_EasyEnsemble.png)

## Summary

Below is the summary of all the Six models:

![Summary](/Resources/Summary.png)

Of all the methods used in this project, Easy Ensemble AdaBoost Classifier has the **highest Balanced Accuracy Score**. The imbalanced classification results printed for each model show that EasyEnsemble also has the **highest precision, recall, and F1 scores**.

Use of *Easy Ensemble AdaBoost Classifier* is advised if one of the models in this project needs to be used to forecast credit risk. However, it is not advised to use any of these models if given the choice. Despite having the greatest performance in this category, the EasyEnsemble model's precision for high-risk data points is still only 0.07. This shows that very few optimistic predictions are TRUE (False Positives).

In order to produce a more reliable model that can anticipate credit risk, additional research and development are necessary.