# **Credit Risk Analysis: A Machine Learning Project**

## *Project Overview*
The purpose of this project was to create a machine learning solution that would be able to predict credit risk. Specifically, the machine learning model that we were looking for needed to be one that able to accurately classify if a loan is **good** or **risky**. Thus, we implemented six different machine learning models in order to assess if any of them should be used to predict credit risk. 

---
## *Results*

As stated above, **six** different machine learning models were tested with the purpose of identifying the best way to predict credit risk. Our target was the **["loan_status"]** column, which divides the loans into two categories: high risk and low risk. As credit risk is usually an imbalanced classification problem (given that, in most cases, the amount of good loans outweigh the number of risky loans), each of these models handles the data in a different way. Thus, each model had varying accuracy, precision and recall scores, which are described section that follows.

---
## *The models*
For each model,  we first created dummies for the data that was in a string format, and then proceeded to split our data into training and testing. These were the results:

### *1. Naive Random Oversampling*

* Balanced accuracy score: **0.66**
* Precision: **0.99** (Total) | **0.01** (High Risk), **1.00** (Low Risk).
* Recall: **0.60** (Total) | **0.71** (High Risk), **0.60** (Low Risk).

![1](https://user-images.githubusercontent.com/113153777/223010469-f49b8d3f-5c36-4781-ab9b-987a4e62d602.png)

### *2. SMOTE Oversampling*
* Balanced accuracy score: **0.66**
* Precision: **0.99** (Total) | **0.01** (High Risk), **1.00** (Low Risk).
* Recall: **0.69** (Total) | **0.63** (High Risk), **0.69** (Low Risk).

![2-1](https://user-images.githubusercontent.com/113153777/223010552-38af9c77-9848-4c54-9afd-12517222ad4a.png)

![2-2](https://user-images.githubusercontent.com/113153777/223010580-eee1e9c8-2f15-415b-ac0e-40bfe1c43ad1.png)

### *3. Cluster Centroids Algorithm (Undersampling)*
* Balanced accuracy score: **0.54**
* Precision: **0.99** (Total) | **0.01** (High Risk), **1.00** (Low Risk).
* Recall: **0.40** (Total) | **0.69** (High Risk), **0.40** (Low Risk).

![3](https://user-images.githubusercontent.com/113153777/223010698-e1be7397-db42-46ce-84a4-c6fd62206761.png)

### *4. SMOTEENN Algorithm (Combination Sampling)*

* Balanced accuracy score: **0.54**
* Precision: **0.99** (Total) | **0.01** (High Risk), **1.00** (Low Risk).
* Recall: **0.57** (Total) | **0.72** (High Risk), **0.57** (Low Risk).

![4-1](https://user-images.githubusercontent.com/113153777/223010783-69c94af9-0be4-49e7-b0bc-1ba6cfb15222.png)

![4-2](https://user-images.githubusercontent.com/113153777/223010801-12a951ba-603d-4c8a-8c76-15b7e03c8e0b.png)

### *5. Balanced Random Forest Classifier*
* Balanced accuracy score: **0.79**
* Precision: **0.99** (Total) | **0.03** (High Risk), **1.00** (Low Risk).
* Recall: **0.87** (Total) | **0.70** (High Risk), **0.87** (Low Risk).

![image](https://user-images.githubusercontent.com/113153777/223010945-9210603e-f411-4aa4-a535-803c474b0548.png)

![image](https://user-images.githubusercontent.com/113153777/223011036-91af2444-87bd-4120-8faf-69104ecd1eb4.png)

### *6. Easy Ensemble AdaBoost Classifier*
* Balanced accuracy score: **0.93**
* Precision: **0.99** (Total) | **0.09** (High Risk), **1.00** (Low Risk).
* Recall: **0.94** (Total) | **0.92** (High Risk), **0.94** (Low Risk).

![image](https://user-images.githubusercontent.com/113153777/223011128-0a133d0d-b9eb-4bda-b49b-32750d9c5db2.png)

![image](https://user-images.githubusercontent.com/113153777/223011187-0504ef0c-cd8c-4625-9646-85c9730d45bc.png)

---
## *Summary*

If we observed the results of each model, we can clearly see that the different ways in which the data is handled had significant impact on their individual performance. 

When it came to models 1-2, which used oversampling, the results were underwhelming, as these models had an accuracy score of 0.66. Models 3 and 4 performed even worse, with a balanced accuracy score of 0.54. For all of these models, precision was very low for high risk loans, while the recall score was average for both types of loans.

Models 5 and 6, which are included in the category of ensemble algorithms, performed much better in comparison. The Balanced Random Forest Classifier gave us an accuracy score of 0.79, as well as a better precision score for high risk loans (at 0.03), and recall scores of 0.70 and 0.87 for high and low risk loans, respectively. 

The last model, which used the Easy Ensemble AdaBoost Classifier, gave us the best performance overall, with an accuracy score of 0.93. The precision score was also higher for high risk loans (0.09), and the recall score was higher than 0.90 for both types of loans.

Now, it is clear that, if any model were to be recommended, it would be one of the ensemble algorithms. Although the precision score is not very high for either of them, both have good recall scores. The choice between them comes down to prioritizing one of two things: the flexibility of the model, or the overall performance. If we were to choose the last model, which performed the best out of all of them, we could risk having an overfitted model (as the score is higher than 90%). The 5th model, by contrast, may have had a lower accuracy score (78%), but could be a more flexible model for new data. Our recommendation would be prioritize model flexibility, as this type of model could be more useful in the future. 
