# Credit-Card-Fraud-Detection
Problem Statement:
Fraudulent activities have increased several fold, with around 52,304 cases of credit/debit card fraudreported in FY'19 alone. Due to this steep increase in banking frauds, it is the need of the hour to detect these fraudulent transactions in time in order to help consumers as well as banks, who are losing their credit worth each day.
Every fraudulent credit card transaction that occur is a direct financial loss to the bank as the bank is responsible for the fraud transactions as well it also affects the overall customer satisfaction adversely.
Aim:
The aim of this project is to identify and predict fraudulent credit card transactions using machine learning models.


Approaches:
The approach to the problem can be divided into below parts:
1.	Understanding of the data, Preparation of the data and EDA
First look at the data used here from the Kaggle dataset suggests that it is highly imbalanced in nature. The positive class (frauds) account for only 0.172% of all transactions:
Class	0	1
Count	284315	492

Class is the target variable which we have to predict where 0 is normal transaction and 1 is fraudulent transaction.
Features V1, V2, … V28 are the principal components obtained with PCA, the only features which have not been transformed with PCA are 'Time' and 'Amount'. Feature 'Time' contains the seconds elapsed between each transaction and the first transaction in the dataset. The feature 'Amount' is the transaction Amount, this feature can be used for example- dependent cost-sensitive learning.
Since the PCA transformed variable are already Gaussian, there is no need for normalization.We can start with the basic EDA like correlation, boxplots etc., for outliers.
Next, we can use transformation to mitigate and check the skew-ness in the data. (Box-cox, Log transformation, Yeo-Johnson etc.)
 
Class Imbalances:
The normal Oversampling method won’t be used here as it does not add any new information to the dataset and Under-sampling will also not be used as it leads to the loss of
information.Next, we will try the below two class imbalance handling techniques:
•	SMOTE is a process where you can generate new data points, which lie vectorically betweentwo data points that belong to the minority class.
•	ADASYN is similar to SMOTE, with a minor change i.e. the number of synthetic samples that it will add will have a density distribution. The aim here is to create synthetic data for minority examples that are harder to learn, rather than the easier ones.
