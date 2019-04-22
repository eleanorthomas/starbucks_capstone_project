# Starbucks Promotion Project Report

## Introduction

The following is adapted from the Udacity exercise description.

The dataset provided in this portfolio exercise was originally used as a take-home assignment provided by Starbucks for their candidates. The data for this exercise consists of about 120,000 data points split in 2:1 ratio among training and test files. Each data point includes one column indicating whether or not an individual was sent a promotion for a specific product, and one column indicating whether or not that individual eventually purchased that product. Each individual also had seven additional features associated with them.

The training data is provided below.

For a full description of what Starbucks provides to candidates see the [instructions available here](https://drive.google.com/open?id=18klca9Sef1Rs6q8DW4l7o349r8B70qXM).

The purpose of this project is to use the training data to understand what patterns in V1-V7 (the training features) to indicate that a promotion should be provided to a user. The expected solution will be a function called promotion_strategy, likely utilizing some form of machine learning classification strategy in order to classify users into two categories: "send promotion" and "do not send promotion". The results will be compared with Starbucks's solution.

The motivation for this project is to satisfy requirements for Term 2 of the Udacity Data Scientist Nanodegree, as well as to practice and demonstrate fundamental data science skills and the data science process.

## Methods Used

Three different classifiers were implemented (GaussianNB, RandomForestClassifier, and AdaBoostClassifier) in order to attempt to classify individual into two categories (Send Promotion = "Yes" or "No") based on whether or not we thought a promotion would be effective in encouraging them to make a purchase. The AdaBoostClassifier was selected as the best possible candidate for optimization, and was further optimized. Two metrics (NIR and IRR) were evaluated to determine the potential (revenue-related) success of the promotion strategy.

## Summary of Results

We were able to beat the random-assignment benchmark value for NIR listed above and come in line with the benchmark value for IRR, but did not reach the highest IRR and NIR values obtained at Udacity.

Given that the classifiers implemented did not do much better than chance levels at predicting whether an individual was flagged for promotion, it is not surprising that the results were not phenomenal. There were also several points in the process where assumptions were made, and it's possible that by going back and revisiting these assumptions individually, performance could be improved.

## Further Areas for Improvement

The first area for improvement I would attempt would be to define the discrete features as categorical variables and re-attempt classification with the new feature set.

The second area for improvement I would consider would be to re-evaluate the definition of the target variable. Perhaps only individuals who received the promotion should be considered for classification, based on whether or not they purchased. Perhaps individuals who did not receive the promotion but purchased anyway should also be considered, and still labeled as "No", but individuals who did not receive the promotion and did not purchase should be excluded from the data set, since they do not offer us very much information and were perhaps simply adding noise to the data.

The final area for improvement that I would consider would be to do a deeper dive into the classifier models and hyperparameter optimization, to see if there is a better model than the ones considered and possibly employ GridSearch on each of the classifiers to be sure we have the best set of hyperparameters for each. I would only pursue this path after exploring the first two areas of improvement, since a more well-defined problem will always yield better results than a fancy algorithm with noisy data and an ill-defined task.

## Acknowledgements

Udacity for starter code and descriptions. Starbucks for generously offering this project and dataset to Udacity students.
