https://www.ibm.com/cloud/blog/supervised-vs-unsupervised-learning
https://www.alteryx.com/glossary/supervised-vs-unsupervised-learning
https://towardsdatascience.com/unsupervised-learning-and-data-clustering-eeecb78b422a
##### Supervised learning:
Uses labelled datasets designed to train or "supervise" algorithms into classifying data or predicting outcomes
Goal : Prediction of outcomes for new data that is introduced
Applications: Spam detection, Processing sentiment analysis

Categorized into:

- [[Classification]] - Assigns test data into specific categories
Eg : Support vector machines, linear classifiers, decision trees
- Regression - Understands the relationship between dependent and independent variables
Eg: Linear regression, logistic regression and polynomial regression

##### Unsupervised learning:

Uses unlabelled datasets to discover hidden patterns in data without human intervention.
Goal : Getting new insights from massive amounts of new data
Applications: Anomaly detection, recommendation engines

- [[Clustering]] - Data mining technique to group unlabelled data based on similarities or differences
- Association - Uses different rules to find the relationship between variables in a given dataset.
- Dimensionality reduction - Used when the number of features is too high. Reduces the number of inputs to a manageable size while preserving data integrity.


Why do we need unsupervised learning?

1.Annotating large data sets is expensive

2.When number of classes/type of classes is unknown

3.Gain insight into the structure of data

Unsupervised learning can be divided into: 

- Parametric unsupervised learning

Assumes that sample data comes from a population that follows a probability distribution based on a fixed set of parameters
Example: [[Clustering#Gaussian Mixture Model|Gaussian Mixture Model]]

- Non-parametric unsupervised learning

The data is grouped into clusters, where each cluster says something about categories and classes present in the data.
Example :  [[K-means clustering]]

#### Semi supervised learning
A training dataset with both labeled and unlabeled data is used. It’s particularly useful when it’s difficult to extract relevant features from data and when there is a high volume of data.