
[https://doi.org/10.1007/978-3-319-67056-0_18](https://doi.org/10.1007/978-3-319-67056-0_18)

#### Text Mining
Gaining insight by extracting information from large unstructured text datasets.
Text mining tools are needed to perform indexing and retrieval of  rapidly growing text data.

#### TF-IDF
The weight of each word is counted with respect to the number of times it is repeated in the text and the number of files in which it exists. Too much repetition means that the word is unimportant. It is used for extracting core words (i.e., keywords) from documents, calculating similar degrees among documents, deciding search ranking, and so on.

#### Bayesian algorithm
A simple method used in text classification. However, it is not highly efficient because it does not model texts well, nor does it provide a good feature selection.

#### Nearest Neighbor algorithm
It was introduced as one of the
most widely-used text classification algorithms due to its simplicity and efficiency in classifying different types of
text. However, determining the effective K parameter to increase the algorithm precision remains a problem.
#### Support Vector Machine
It  is a text classification technique
based  on the lowest structural risk principle. During training, this
algorithm creates a hyper plane for separating positive and negative samples. Then it classifies new samples by
specifying where on the hyper plane, each sample must be placed. Considered to be one of the best classification algorithms for emotion recognition in sentences. It supports data with high dimensions.

Aim : Classify news into various groups so that users can identify the most popular news group in the desired country at
any given time

Approach : Text preprocessing, feature selection based on TF-IDF, and text
classification using SVM. BBC and 20Newsgroup datasets are
used to evaluate the proposed method

Features : subject and body of each news article

Results:
The classification precision was
obtained 97.48% for the BBC dataset and 94.93% for the 20Newsgroup dataset respectively. Through this classification, insight gained : 
best group in the BBC set to be
sports with 99.22%, and the best
group was politics in the 20Newsgroup dataset with 97.34%

