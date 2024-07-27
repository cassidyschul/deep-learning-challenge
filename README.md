# deep-learning-challenge
Module 21 Challenge
## Overview of the Analysis
The purpose of the analysis is create a neural networks model that can predict whether applicants will be successful if funded by Alpheabetical Soup. The data provided general and financial information regarding successful and unsuccessful applicants such as organization type, income amount, asking amount, affiliated industry, etc. 

First, the data was preprocessed and cutoffs were established for features that had many unique values. The categorical data was then converted to numeric, split into training and testing sets, and scaled. A neural network Sequential model was created and trained using various input dimensions, activation functions and nodes. The model was compiled, trained and evaluated. This process was optimized to achieve a predictive accuracy greater than 75%. 

## Results

The target variable in all models was the 'IS_SUCCESSFUL' value, one meaning the applicant was successful and zero meaning the applicant was not successful. In the provided dataset, there were 18261 successful applicants and 16038 unsuccessful applicants. 

* Machine Learning Model 1:
    * Neural Network Model 1: 
        * Features: APPLICATION_TYPE, AFFILIATION, CLASSIFICATION, USE_CASE, ORGANIZATION, STATUS, INCOME_AMT, SPECIAL_CONSIDERATIONS, ASK_AMT
        * Non-benefitical columns: EIN, NAME
        * This model included three layers. The first (8 neurons) and second (5 neurons) layers used the relu activation function and the output layer used the sigmoid activation function. These activiation functions were selected because they are most commonly used in neural network model development. 
        * Accuracy: 0.7276
        * Loss: 0.5557
        * This model was not able to achieve target performance, optimization was required. 
    
    * Neural Network Model Optimization 1:
        * Features: APPLICATION_TYPE, AFFILIATION, CLASSIFICATION, USE_CASE, ORGANIZATION, INCOME_AMT, ASK_AMT
        * Non-benefitical columns: EIN, NAME, STATUS, SPECIAL_CONSIDERATIONS
        * In this model, the number of bins was increased for the APPLICATION_TYPE (cutoff = 100) and CLASSIFICATION (cutoff = 500) features
        * This model included three layers. The first (80 neurons) and second (80 neurons) layers used the relu activation function and the output layer used the sigmoid activation function. These activiation functions were selected because they are most commonly used in neural network model development. 
        * The number of epochs was increased to 200. 
        * Accuracy: 0.7287
        * Loss: 0.5708
        * This model was not able to achieve target performance, further optimization was required.

    * Neural Network Model Optimization 2:
        * Features: APPLICATION_TYPE, AFFILIATION, CLASSIFICATION, USE_CASE, ORGANIZATION, INCOME_AMT, ASK_AMT
        * Non-benefitical columns: EIN, NAME, STATUS, SPECIAL_CONSIDERATIONS
        * In this model, the number of bins was increased for the APPLICATION_TYPE (cutoff = 50) and CLASSIFICATION (cutoff = 10) features. 
        * This model included four layers. The first (400 neurons), second (200 neurons), and third (200 neurons) layers used the relu activation function and the output layer used the sigmoid activation function. These activiation functions were selected because they are most commonly used in neural network model development. 
        * The number of epochs was decreased to 50. This value was decreased because it did not improve performance when increased in the first model optimization.
        * Accuracy: 0.7292
        * Loss: 0.5842
        * This model was not able to achieve target performance, further optimization was required.

    * Neural Network Model Optimization 3:
        * Features: APPLICATION_TYPE, AFFILIATION, CLASSIFICATION, USE_CASE, ORGANIZATION, INCOME_AMT, ASK_AMT
        * Non-benefitical columns: EIN, NAME, STATUS, SPECIAL_CONSIDERATIONS
        * In this model, the number of bins was increased for the APPLICATION_TYPE (cutoff = 5) and CLASSIFICATION (cutoff = 5) features. 
        * This model included three layers. The first (512 neurons) and second (256 neurons) layers used the relu activation function and the output layer used the sigmoid activation function. These activiation functions were selected because they are most commonly used in neural network model development. The number of layers were decreased because it did not improve performance when increased in the second model optimization. The number of neurons was increased to investigate if it impacted performance. 
        * The learning rate of the optimizer was lower to 0.0001 from the default (0.001) to investigate if this would improve performance.
        * The number of epochs remained set at 50. 
        * Accuracy: 0.7315
        * Loss: 0.5524
        * This model was not able to achieve target performance, further optimization is required.

## Summary

The original neural network model produced the lowest accuracy percentage. Various parameters were altered to improve the model. The best neural network model was the third optimization model. Althought none of the models produced above a 75% predictive accuracy, this model produced the greatest accuracy and smallest loss. It should be noted that the all models produced very similar accuracy and loss results. Futher, the test set accuracy value and training set accuracy values are close, indicating the model is not overfitting.  Overall, I recommend the model for applicant success prediction. 

Another type of model that I would recommend using in this scenario is a LogisticRegression model since this is a binary classification problem. A LogisticRegession model is simplier, has shorter training times, and could produce similary predictive accuracy. 
