# deep-learning-challenge
Module 21 Challenge
## Overview of the Analysis

In this section, describe the analysis you completed for the machine learning models used in this Challenge. This might include:

The purpose of the analysis is create a neural networks model that can predict whether applicants will be successful if funded by Alpheabetical Soup. The data provided general and financial information regarding successful and unsuccessful applicants such as organization type, income amount, asking amount, affiliated industry, etc. 

The target variable in this analysis was the 'IS_SUCCESSFUL' value, one meaning the applicant was successful and zero meaning the applicant was not successful. In the provided dataset, there were 18261 successful applicants and 16038 unsuccessful applicants. 

First, the data was preprocessed and cutoffs were established for features that had many unique values. The categorical data was then converted to numeric, split into training and testing sets, and scaled. A neural network Sequential model was created and trained using various input dimensions, activation functions and nodes. The model was compiled, trained and evaluated. This process was optimized to achieve a predictive accuracy greater than 75%. 
