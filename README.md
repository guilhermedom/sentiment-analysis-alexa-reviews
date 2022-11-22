# Sentiment Analysis on Amazon's Alexa Reviews

Fully connected neural network analyzing sentiments in reviews for Amazon's Alexa.

---

## Problem Overview

[Sentiment analysis] is a growing field of study where feelings and opinions of individuals are mined from text data. The most common objective is to evaluate user feedback on products or services.

Neural networks have been successfully applied to this task to understand users and provide a deep understanding of their expectations. Even shallow networks have been able to get promising results surpassing many other machine learning algorithms. As expected, [natural language processing] (NLP) is highly associated with these great results.

For this project in particular, we aim to predict the feedback of Amazon's Alexa buyers. We use a [dataset] built by collecting reviews posted on Amazon's website. In this dataset, there are 3150 reviews (or instances) with 4 predictor variables and 1 response variable ("feedback"). The next table provides a summary on each attribute in this dataset.

| Attribute | Summary |
|:------:|:---------------------:|
| Rating | A rating, from 1 to 5 stars, given by the buyer for the purchased product. |
| Date | The date the review was posted. |
| Variation | Alexa model purchased by the reviewer. |
| Verified reviews | Textual comment provided by the reviewer. |
| Feedback | 0, if the feedback is negative; 1, if the feedback is positive. |

## Analysis Introduction

We perform two analyses using two different dataset versions. For the first version, that has the rating attribute, we develop a fully-connected neural network and predict the feedback on the testing portion of the dataset. For the second version of the dataset, not having the rating attribute, we create another fully-connected neural network. A different architecture is needed for the second version of the dataset since the data becomes very sparse and, therefore, very susceptible to overfitting. In this second version, the model focus mainly on the bag of words constructed using review comments.

In both cases, the accuracy metric stays well above 90%. It is important to remember, however, that accuracy is not a good metric to evaluate tasks with imbalanced classes. Nonetheless, the two other metrics, [area under the ROC curve] and [area under the PR curve], confirm that our model achieves a great performance. When using the rating variable, the most correlated one to the response variable, a near-perfect performance is achieved: around 0.99 in all metrics. The figure below shows the training progression for our first model, the one working with the rating variable:

![sentiment_analysis_alexa_reviews_validation_accuracy](https://user-images.githubusercontent.com/33037020/203198842-7725a24c-bfc0-409e-b6b1-3523dcbffde0.PNG)

[//]: #

[Sentiment analysis]: <https://en.wikipedia.org/wiki/Sentiment_analysis>
[natural language processing]: <https://www.ibm.com/cloud/learn/natural-language-processing>
[dataset]: <https://www.kaggle.com/datasets/sid321axn/amazon-alexa-reviews>
[area under the ROC curve]: <https://scikit-learn.org/stable/modules/model_evaluation.html#roc-metrics>
[area under the PR curve]: <https://scikit-learn.org/stable/modules/model_evaluation.html#precision-recall-f-measure-metrics>
