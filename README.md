# Stack-overflow-tag-prediction

Dataset Link: https://www.kaggle.com/imoore/60k-stack-overflow-questions-with-quality-rate

## Description

Stack Overflow is the largest, most trusted online community for developers to learn, share their programming knowledge, and build their careers. Stack Overflow is something which every programmer use one way or another. Each month, over 50 million developers come to Stack Overflow to learn, share their knowledge, and build their careers. It features questions and answers on a wide range of topics in computer programming. The website serves as a platform for users to ask and answer questions, and, through membership and active participation, to vote questions and answers up or down and edit questions and answers in a fashion similar to a wiki or Digg. As of April 2014 Stack Overflow has over 4,000,000 registered users, and it exceeded 10,000,000 questions in late August 2015. Based on the type of tags assigned to questions, the top eight most discussed topics on the site are: Java, JavaScript, C#, PHP, Android, jQuery, Python and HTML.

## Real World / Business Objectives and Constraints

Predict as many tags as possible with high precision and recall.
Incorrect tags could impact customer experience on StackOverflow.
No strict latency constraints.

## Data Overview

All of the data is in 2 files: Train and Test.

- Train.csv contains 4 columns: Id,Title,Body,Tags.
- Test.csv contains the same columns but without the Tags, which you are to predict.
- Size of Train.csv - 6.75GB
- Size of Test.csv - 2GB
- Number of rows in Train.csv = 6034195

The questions are randomized and contains a mix of verbose text sites as well as sites related to math and programming. The number of questions from each site may vary, and no filtering has been performed on the questions (such as closed questions).

Data Field Explaination
Dataset contains 6,034,195 rows. The columns in the table are:

- Id - Unique identifier for each question
- Title - The question's title
- Body - The body of the question
- Tags - The tags associated with the question in a space-seperated format (all lowercase, should not contain tabs '\t' or ampersands '&')

## Type of Machine Learning Problem

It is a multi-label classification problem
Multi-label Classification: Multilabel classification assigns to each sample a set of target labels. This can be thought as predicting properties of a data-point that are not mutually exclusive, such as topics that are relevant for a document. A question on Stackoverflow might be about any of C, Pointers, FileIO and/or memory-management at the same time or none of these.
__Credit__: http://scikit-learn.org/stable/modules/multiclass.html

## Performance metric
- Micro-Averaged F1-Score (Mean F Score) : The F1 score can be interpreted as a weighted average of the precision and recall, where an F1 score reaches its best value at 1 and worst score at 0. The relative contribution of precision and recall to the F1 score are equal. The formula for the F1 score is:

F1 = 2 * (precision * recall) / (precision + recall)

In the multi-class and multi-label case, this is the weighted average of the F1 score of each class.

- 'Micro f1 score':
Calculate metrics globally by counting the total true positives, false negatives and false positives. This is a better metric when we have class imbalance.

- 'Macro f1 score':
Calculate metrics for each label, and find their unweighted mean. This does not take label imbalance into account.

https://www.kaggle.com/wiki/MeanFScore
http://scikit-learn.org/stable/modules/generated/sklearn.metrics.f1_score.html

- Hamming loss : The Hamming loss is the fraction of labels that are incorrectly predicted.
https://www.kaggle.com/wiki/HammingLoss

## Plots for better understanding

### Countplot of Tags per question

![a1](https://user-images.githubusercontent.com/58303643/179389080-083a53c5-2f28-4eb9-a1df-4fe5fdd67e71.jpg)

### Distribution of Tags

![a2](https://user-images.githubusercontent.com/58303643/179389127-e810d01f-20f5-419b-b7d5-d8fd52bcfb57.jpg)

### WordCloud

![a3](https://user-images.githubusercontent.com/58303643/179389150-65ff8051-801d-4793-9ec3-8306a3b32f43.jpg)

## Strategy:

1. Libraries
2. Data Cleaning – Stage 1
3. Analysis of Tags
4. Tag Plots
5. Data Cleaning – Stage 2
6. Training Data
7. Testing Data
8. Machine Learning
9. Splitting the training Data
10. Tags Reduction
11. Removing no coverage
12. Featurizing data with TF-IDF vectorizer
13. Featurizing Labels
14. OneVsRest Classifier with SGDClassifier using TF-IDF

## Results 

![a4](https://user-images.githubusercontent.com/58303643/179389294-71fe28d0-a541-47b6-8f91-445c907202c7.png)





