[https://levity.ai/blog/what-is-topic-modeling#:~:text=Topic%20modeling%20is%20a%20type,predefined%20tags%20or%20training%20data]
https://towardsdatascience.com/end-to-end-topic-modeling-in-python-latent-dirichlet-allocation-lda-35ce4ed6b3e0
https://link.springer.com/article/10.1007/s11042-018-6894-4

It is an [[Supervised versus unsupervised learning#Unsupervised learning|unsupervised machine learning]] statistical modelling technique used to identify clusters or groups within a body of text. Themes are identified within text to form the clusters. Great for representing discrete data.
Used for document classification, tagging customer support tickets and analyzing customer feedback


Topic models in text document analysis do not understand the meanings of words. Instead, they assume that words in a document are selected from predefined topic baskets. The topic modeling process repeats to determine the most likely distribution of words into topics. This approach provides a helpful perspective on large collections, considering the collection as a whole, individual documents, and the relationships between them.
#### Working

Similar word patterns are grouped into topics to create topic clusters. It can be thought of as a combination of 3 processes:

##### Dimensionality reduction : 
Text is represented in topic space instead of feature space by taking the weight of the words in the text instead of their count.

##### Unsupervised Clustering
A cluster of words is built instead of a cluster of texts. A text thus becomes a mixture of all the topics, each with their own weights

##### Tagging
Getting the abstract topics that occur in a collection of documents that best represents the information contained within them.


[[Latent Dirichlet Allocation]]

- Each topic is a mixture over an underlying set of words, and each document is a mixture of over a set of topic probabilities.

●Uncovers the hidden structure in a set of observations by looking at the relationships between words in a document and grouping them into topics.

●Matching topics in two documents can be analyzed and specific groups for each topic can be created. This way, you create a document term matrix, an interconnected network of topics, and analyze multiple documents to classify their contents, text, image, and more

# **Parameters of LDA**

> **Alpha parameter** is Dirichlet prior concentration parameter that represents document-topic density — with _a higher alpha, documents are assumed to be made up of more topics and result in more specific topic distribution per document._
> 
> **Beta parameter** is the same prior concentration parameter that represents topic-word density — _with high beta, topics are assumed to made of up most of the words and result in a more specific word distribution per topic._

Methods to estimate the parameters:

- Gibbs sampling - a method of generating a sample from a joint distribution when only conditional distributions of each variable can be efficiently computed
- Expectation Maximization - the algorithm relies on discovering the maximum likelihood estimates of parameters when the data model depends on certain latent variables EM algorithm contains two steps, the E-step (expectation) and the M-step (maximization)
- Variational Bayes inference -  uses a parametric approximation to the posterior distribution of both parameters and other latent variables and attempts to optimize the fit (e.g. using KL-divergence) to the observed data.

LSA
●LSA is based on the principle that words that are close in meaning tend to be used together in context.

●LSA assumes all similar documents to share the same patterns when their word frequency and order are consistent, which helps analyze not just one but a collection   of documents.


#### [[Topic Modelling]] versus [[Clustering]]

_Topic Modelling_
●A statistical technique that discovers latent topics in a collection of documents. 

●Finds relationships between items and understands a dataset's hidden structure.

●Doesn’t require manual labeling of the data points


_Clustering_
● Machine Learning method for grouping together similar data points

●Typically used to group items together so that they can be analyzed as a whole.

●Requires manual labeling of the data points

#### Topic Modelling versus Topic Classification

_Topic Modelling_
●More general unsupervised approach used for any type of data

●Finds latent topics in a collection of documents

_Topic Classification_
●More specific supervised approach that categorizes documents into predefined topics

●Assigns a label to a document     according to its topic

#### Topic Modelling versus [[Text Classification]]

_Topic Modelling_

●Unsupervised

●Can find hidden structure in text data

●More flexible since it doesn’t require a predefined set of categories

_Text Classification_

●Supervised

●More focused on assigning labels to texts

●Less flexible as it requires pre-labelling of the data

