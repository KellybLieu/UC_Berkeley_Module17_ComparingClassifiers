
## UC Berkeley Module17 Comparing Classifiers By Kelly Lieu
 GOAL--
 Practical application assignment. Goal is to compare the performance of the classifiers, K Nearest Neighbor, Logistic Regression, Decision Trees, and Support Vector Machines utilizing a dataset related to marketing bank products over the telephone.

 OVERVIEW---
 In this practical application, our goal is to compare the performance of the classifiers we encountered in our class, namely K Nearest Neighbor, Logistic Regression, Decision Trees, and Support Vector Machines. We will utilize a dataset related to marketing bank products over the telephone.
 
 GETTING STARTED---
 Our dataset comes from the UCI Machine Learning repository link: https://archive.ics.uci.edu/dataset/222/bank+marketing. The data is from a Portugese banking institution and is a collection of the results of multiple marketing campaigns. We will make use of the article accompanying the dataset here for more information on the data and features.
 
 BUSINESS OBJECTIVE---
 Our business objective is to leverage Business Intelligence and Data Mining tools to uncover attributes or patterns that can increase effectiveness of marketing strategies and campaigns for better key performance indicators (KPIs).
 
 In this exercise, our data scientists will split up into 4 teams, each team will build a different algorithm, Logistic Regression, K Nearest Neighbor, Decision Trees, and Support Vector Machines. Then we will compare the performance of the classifiers using different metics. Finally, our team will provide visualization of the results and a recommendation to marketing managers.

 OUTLINE
 This Assignment will consist of this README, dataset, and Jupyter notebook the contains the step-by-step methodology implemented and written in Python to arrive at our findings. The overall outline of steps are:
 1) Reading the data
 2) Understanding features
 3) Understanding the tasks
 4) Defining the business objectives
 5) Feature engineering and preprocessing data
 6) Setting up training and test data
 7) Starting with a baseline model
 8) Building a simple model
 9) Building, comparing multiple models by various metrics, and visualizing
 10) Improving models by hyperparameter tuning and grid search
 11) Finding the best features and provide recommendation in output
 
INPUT VARIABLES---
//bank client data:
1 - age (numeric)
2 - job : type of job (categorical: 'admin.','blue-collar','entrepreneur','housemaid','management','retired','self-employed','services','student','technician','unemployed','unknown')
3 - marital : marital status (categorical: 'divorced','married','single','unknown'; note: 'divorced' means divorced or widowed)
4 - education (categorical: 'basic.4y','basic.6y','basic.9y','high.school','illiterate','professional.course','university.degree','unknown')
5 - default: has credit in default? (categorical: 'no','yes','unknown')
6 - housing: has housing loan? (categorical: 'no','yes','unknown')
7 - loan: has personal loan? (categorical: 'no','yes','unknown')
//related with the last contact of the current campaign:
8 - contact: contact communication type (categorical: 'cellular','telephone')
9 - month: last contact month of year (categorical: 'jan', 'feb', 'mar', ..., 'nov', 'dec')
10 - day_of_week: last contact day of the week (categorical: 'mon','tue','wed','thu','fri')
11 - duration: last contact duration, in seconds (numeric). Important note: this attribute highly affects the output target (e.g., if duration=0 then y='no'). Yet, the duration is not known before a call is performed. Also, after the end of the call y is obviously known. Thus, this input should only be included for benchmark purposes and should be discarded if the intention is to have a realistic predictive model.
//other attributes:
12 - campaign: number of contacts performed during this campaign and for this client (numeric, includes last contact)
13 - pdays: number of days that passed by after the client was last contacted from a previous campaign (numeric; 999 means client was not previously contacted)
14 - previous: number of contacts performed before this campaign and for this client (numeric)
15 - poutcome: outcome of the previous marketing campaign (categorical: 'failure','nonexistent','success')
//social and economic context attributes
16 - emp.var.rate: employment variation rate - quarterly indicator (numeric)
17 - cons.price.idx: consumer price index - monthly indicator (numeric)
18 - cons.conf.idx: consumer confidence index - monthly indicator (numeric)
19 - euribor3m: euribor 3 month rate - daily indicator (numeric)
20 - nr.employed: number of employees - quarterly indicator (numeric)

OUTPUT VARIABLE---
[desired target]
21 - y - has the client subscribed a term deposit? (binary: 'yes','no')

SUMMARY OF INITIAL RESULTS---
From comparing the performance of 5 classifiers, including the baseline model, the results show that Logistic Regression classifier performed the best. This determination was based on evaluating which model had the highest test accuracy. The bar chart above shows the best performing models in decending order from left to right (e.g., Linear Regression, SVM, KNN, Baseline, Decision Tree).

HYPERPARAMETER TUNING RESULTS---
After tuning the hyperparameters for each model, the best performing models ranked differently from the models before hyper-parameter tuning. Post-tuning, the best performing model is ranked by Test  Accuracy in decending order:

1) Decision Tree with 91.51%
2) Sequential Vector Machine with 91.18%
3) Logistic Regression with 91.14%
4) K Nearest Neighbors with 90.42%
5) Baseline model with 88.65%

This exercise shows the significance and importance of tuning hyperparameters to improve the outcome of machine learning.
The results are visualized and will be provided to the customer for further analysis.

CUSTOMER RECOMMENDATION---
In addition, with Decision Tree as the classifier that performed the best, our team went on to rebuild the decision tree individually and extract the best features. The top 2 features with the higest importance scores:

1) Duration ("duration" in seconds)
2) Number of Employees ("nr.employed" quarterly)

The Decision Tree algorithm predicts that longer duration of contact will increase the higher the likelihood of a potential buying customer by 44.87%. The classifier predicts that the second feature, number of employees, indicates that a higher number of employees will have a 24.85% likelihood that a customer would potentially buy. In other words, the algorithm recommends: 
1) focusing on increasing the duration of contact with a potential buying customer
2) focusing on customers who work for companies with larger number of employees to improve the outcome of the marketing campaigns.

The decision tree algorithm will be provided to the customer for further analysis.
