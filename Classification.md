
https://deepchecks.com/glossary/binary-classification/

https://www.simplilearn.com/tutorials/machine-learning-tutorial/classification-in-machine-learning

https://machinelearningmastery.com/types-of-classification-in-machine-learning/

https://monkeylearn.com/blog/classification-algorithms/


In supervised learning, the model learns by example. It is categorized into:
- Classification
- Regression

The process of organizing structured or unstructured data into a set of classes is Classification. Classification algorithms applied to the training data find the same pattern (similar number sequences, words or sentiments, and the like) in future data sets.

#### Learners in Classification Problems

###### Lazy Learners
A lazy learner stores the training dataset and waits for the test dataset. It uses the training data to make predictions, focusing more on finding the best matching data rather than extensive training. 
Examples: case-based reasoning and the KNN algorithm.

###### Eager Learners
A classification model is built before test dataset is obtained. More time is spent on studying the data than predicting.
Examples: ANN, Naive Bayes, and Decision trees

### Classification Predictive Modeling

A classification problem in machine learning is one in which a class label is anticipated for a specific example of input data.

3 main Classification types:
- Binary - 2 Classes, 1 class represents normal condition, the other class represents aberrant condition
Applications : Spam detection, churn forecast

- Multi-class classification - More than 2 classes. Data is assigned to one of many predefined classes
Applications : Categorization of faces, classification of plant species

- Multi-label classification - 2 or more class labels. Data can be classified to one or more class labels. 
Applications : Photo classification

- Imbalanced classification - Used when there is an unequal distribution of classes in the training dataset
Applications : Fraud detection, outlier detection

Popular classification Algorithms:

#### Logistic regression
The logistic function, also called the sigmoid function is an S-shaped curve that can take any real-valued number and map it into a value between 0 and 1, but never exactly at those limits.
- Logistic regression is used for binary classification where the dependent variable can take only two values, as either one or yes, representing success, or as 0 or no, representing failure.
Applications: Identifying the risk factor for diseases, weather predictions
### Naive Byes
Naive Bayes is commonly used for text analysis, where it determines the probability of a data point belonging to a certain category. Works well even with large datasets.
Applications : Disease prediction, document classification

### K-Nearest Neighbors
 Lazy learning algorithm that calculates the likelihood of a data point belonging to a group based on its closest neighbors.
 Applications : Handwriting detection, image recognition

### Decision Tree

 Excel in classification problems, dividing data points into different groups based on their attributes. Similar to a flow chart, it divides data points into two similar groups at a time, starting with the "tree trunk" and moving through the "branches" and "leaves" until the categories are more closely related to one another.
 Applications: Pattern recognition, identifying diseases
#### Support Vector Machine
Creates a separation between categories by maximizing the distance between data points.
Applications: Business applications for comparing the performance of a stock over a period of time, classification of applications requiring accuracy and efficiency

## Evaluating a Classification Model

### Confusion Matrix
- The matrix provides a summary of the accuracy of a classification model by showing the number of correct and incorrect predictions.
#### Log Loss or Cross-Entropy Loss
- Is a measure used to evaluate the performance of classification models, with lower values indicating better performance.
### AUC-ROC Curve

- AUC is for Area Under the Curve, and ROC refers to Receiver Operating Characteristics Curve.
 - It is a graphical representation of the performance of a classification model, showing the trade-off between true positive rate and false positive rate at different thresholds.

## Classifier Evaluation
### Cross-Validation
It is a technique for evaluating the performance of a classification model by dividing the data into multiple subsets for training and testing.

### Holdout Method
Involves splitting the data into separate train and test sets, with the test set used to evaluate the model's prediction ability.

### ROC Curve
-  It is used to evaluate the performance of a classification model by plotting the relationship between false positive rate and true positive rate.
- Area under the ROC curve (AUC) provides a measure of the accuracy of a multi-class classification model

#### Bias and Variance
- Bias is the difference between actual and predicted values in a model. It represents the assumptions made by the model about the data and directly corresponds to the patterns found in the data. High bias indicates that the model's assumptions are too basic, leading to underfitting.
- Variance is the model's sensitivity to fluctuations in the data. It measures how much the model learns from noise and trivial features, leading to overfitting. A high variance model captures all the features of the given data but may not generalize well to new data.
#### Precision and Recall measures
- Precision is a metric used to determine the model's ability to correctly classify values. It is calculated by dividing the number of correctly classified data points by the total number of classified data points for a specific class label. Precision indicates how well the model classifies data points for a particular class.
- Recall measures the model's ability to predict positive values correctly. It answers the question, "How often does the model predict the correct positive values?" Recall is calculated by dividing the number of true positives by the total number of actual positive values. It indicates the model's predictive ability for positive values.