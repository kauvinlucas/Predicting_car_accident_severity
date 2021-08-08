# Predicting car accident severity
### Capstone Project for the IBM Data Science Professional Certificate
  
  Start date: Sep 05, 2020
  
  End date: Sep 11, 2020


## Introduction
Car road accidents are the number one problem in US road transportation, accounting for 99% of transportation injuries and representing an economic cost of 150 billion USD annually [1]. Deaths and injuries from the accidents are some of the issues concerned by insurance companies, healthcare institution and governments. It’s very important for them to be able to predict the severity rate of an accident given some known variables. This project will attempt to employ classification models to predict severity rates and compare the accuracy of each built model.

## Business problem
Predicting car accidents severity is one of the biggest challenges faced by many actors. No single factor can help in explaining the severity of an accident, and the relationship between these factors, although intuitively positive, are mostly unclear from a statistical point of view. But while each accident may be unique, accumulating insights from each accident may show macro trends and thus allow us to make accurate predictions, which might aid the actors in their decision-making processes. Taking these several seemly uncorrelated variables into a single accurate prediction model is a long process that requires finding generalizable predictive patterns. That can only be achieved by using machine learning algorithms.

## Methodology
The used data was produced by the Seattle government. It describes the accidents occurred between 2004 and 2020 in the city, along with severity codes. The severity codes are labeled as numbers between 0 and 3, from least to most severe. The data had 37 features. Before the Feature Selection stage, two more features were added: “INCHOUR” and “ISHOLIDAY”. The selected features were as presented in the table 1:

#### Table 1 - selected features descriptions
| Feature name       | Description     | Comments     |
| :------------- | :----------: | -----------: |
| SEVERITYCODE | A code that corresponds to the severity of the collision: less and more severe (2 categories)   | This will be the output variable   |
| ADDRTYPE| A description of the collision address type | It may affect collision severity |
| INATTENTIONIND| Whether the person was not paying attention | It may affect collision severity |
| UNDERINFL| Whether the person was driving under the influence of alcohol | It may affect collision severity |
| WEATHER| A description of the weather conditions during the time of the collision | It may affect collision severity |
| ROADCOND| The condition of the road during the collision | It may affect collision severity |
| LIGHTCOND| The light conditions during the collision| It may affect collision severity |
| SPEEDING| Whether or not speeding was a factor in the collision| It may affect collision severity |
| INCHOUR| Hour of the day when the collision has occurred | Newly created dimension. It may affect collision severity |
| ISHOLIDAY| Whether or not collision has occurred in holiday | Newly created dimension. It may affect collision severity |

The data was described by using maps and histograms. Pre-processing of the data included transformation by Feature Selection, enconding by using one hot encoding and binary encoding, Feature Reduction and Normalization.

The following classification algorithms were employed to predict and evaluate the data:
1.	K Nearest Neighbours (KNN)
2.	Decision Tree
3.	Logistic Regression
4.	Random Forest
5.	Support Vector Machine (SVM)

## Results
The choice of k for the k-nearest neighbors algorithm largely depends on the data, and it may change on each evaluation because of the randomly sampled data. To always choose the best k, a heuristic technique called hyperparameter optimization was employed. The training has returned an accuracy score of 65,82% for the training set, and 65,47% for the test set.

The decision tree model had an accuracy score of 65,93%, while the support vector machine had an accuracy of 66,23% and logistic regression a 61,93% of accuracy.
The models were evaluated and reported by using Jaccard score, F1 score and log loss. The results are displayed in the table 2.

#### Table 2 - final report
| Algorithm       | Jaccard     | F1-score     | LogLoss    |
| :------------- | :----------: | -----------: | -----------: |
| KNN | 0.65  | 0.61  | NA |
| Decision Tree | 0.65 | 0.54 | NA |
| SVM | 0.66 | 0.53 | NA |
| Logistic Regression | 0.66 | 0.61 | 0.63 |

## Conclusions
In this project, we analyzed the dataset of car accident severity to predict the severity of the accident by employing supervised machine learning models. After carefully
preprocessing the dataset, which included sampling and feature selection and extraction, the data was modeled by using 4 models: k-nearest neighbors, decision trees, support vector machine and logistic regression.
The outcome variable (severity code) was treated as a binary dependent variable since it only has two categories (less severe and more severe). Keeping that in mind, the model most suitable for predicting the car accident severity rates with the current dataset is the logistic regression. 

### References
[1] NHTSA 2020 Report - https://one.nhtsa.gov/nhtsa/whatis/planning/2020Report/2020report.html
