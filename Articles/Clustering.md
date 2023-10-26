https://towardsdatascience.com/unsupervised-learning-and-data-clustering-eeecb78b422a

https://sodalab.monday.com/boards/5034134212/pulses/5068749604

https://oneai.com/learn/text-clustering

- Clustering is more difficult than supervised classification because there are no labels attached to patterns in clustering.
- Clustering relies on numeric data to represent features of patterns, and information about relationships among patterns can only be extracted through numeric arithmetic.
- Different clustering approaches exist because there is no precise definition of a "cluster".
- Hierarchical clustering methods involve iteratively dividing patterns using a top-down or bottom-up approach. Agglomerative follows a bottom-up approach, while divisive follows a top-down approach.
- Hierarchical methods can lead to the formation of dendrograms, but they lack robustness and are sensitive to noise and outliers. They also have high computational costs.
- Partition clustering methods assign data into k-clusters without hierarchical structure by optimizing a criterion function.
- Partition-based algorithms like k-means and fuzzy c-means have their own advantages and disadvantages, such as defining the number of clusters, susceptibility to local optima, sensitivity to outliers, and ability to handle incomplete or noisy data.

Distance based clustering:

Members in a cluster is close to eachother
Members in a cluster are far away from members in a different cluster

Best clustering solution is determined by proximity measures:

Proximity: How similar/dissimilar the samples are with respect to each other.

i.Similarity measure S(xi,xk): large if xi,xk are similar

ii.Dissimilarity(or distance) measure D(xi,xk): small if xi,xk are similar

i.Vectors: Cosine Distance

ii.Sets: Jaccard Distance

iii.Points: Euclidean Distance

Clustering Algorithms are classified into :
- Exclusive overlapping - Each datapoint belongs strictly to only one cluster
Example - [[K-means clustering]]
- Overlapping cluster - Each datapoint belongs to 2 or more clusters with different degrees of membership
Example : Fuzzy k-means
- Hierarchical clustering - Union between 2 nearest clusters
Example : Hierarchical Agglomerative Clustering
- Probabilistic Clustering - Uses probabilities for clustering
Example :  Gaussian Mixture model

#### Fuzzy K- means
- Fuzzy k-means is a variation of the k-means algorithm that uses weighted centroids based on probabilities.
- The initialization, iteration, and termination processes in fuzzy k-means are the same as those in k-means.
- Unlike k-means, fuzzy k-means results in clusters that are analyzed as probabilistic distributions rather than a strict assignment of labels.
-  k-means can be seen as a special case of fuzzy k-means, where the probability function used assigns a value of 1 if a data point is closest to a centroid, and 0 otherwise.

#### Hierarchical Agglomerative Clustering
- Each item is initially assigned to its own cluster. 
- The distances (or similarities) between the clusters are based on the distances (or similarities) between the items they contain. 
- The process then involves merging the closest pair of clusters into a single cluster and recalculating distances (or similarities) between the new cluster and the remaining clusters.
- This merging and distance computation is repeated until all items are grouped into a single cluster.

#### Gaussian Mixture Model

- A mixture model is a combination of multiple component distributions that together form a mixture distribution.
- The component distributions represent different subpopulations or clusters within the overall dataset.

$$ f(x) = \sum_{k=1} ^{K} \alpha_k f_k(x)$$
- The αk parameter represents the contribution or weight of the kth component in constructing the overall mixture distribution.


Expectation Maximization Algorithm

- Guess values for model parameters
- **E-step**: For each datapoint that has missing values, use the model equation to solve for the distribution of the missing data given the current guess of the model parameters and given the observed data
- With the distribution for each missing value, the _expectation_ of the likelihood function with respect to the unobserved variables can be calculated. 
- If the guess for the model parameter was correct, this expected likelihood will be the actual likelihood of the observed data; if the parameters were not correct, it will just be a lower bound.
- **M-step**: With the expected likelihood function with no unobserved variables in it, maximize the function, to get a new estimate of the model parameters.
- Repeat until convergence.

**_Problems associated with clustering_**

There are a number of problems with clustering. Among them:

- Time complexity when dealing with large datasets
-  If an _obvious_ distance measure doesn’t exist it has to be defined which is not easy in multidimensional spaces
- The result of the clustering algorithm can be interpreted in different ways, so it is not always consistent.


### Text Clustering
Groups similar documents or sentences based on their content and meaning facilitating efficient categorization and analysis of large volumes of information

##### Flat or Hierarchical
Flat - Data categorized into separate fixed sections 
Hierarchical - Captures more nuanced relationships between words and sentences. Modelled like a tree where larger branches have smaller branches to finally end in leaves.
		- Agglomerative -  Starts with individual text documents as leaves and then merges them into larger branches
		- Divisive -  Starts with all the text documents grouped together and then splits them into smaller branches

##### Based on overlaps

Soft clustering - Data instances can belong to multiple categories based on the relevance
Hard clustering  - Each data instance can only belong to one cluster each

##### Based on Goals
Monothetic Clustering - Only one feature is used for clustering
Polythetic Clustering - Multiple features are used for clustering
##### Commonly used Text Clustering methodologies
- Distance measures: Cosine Similarity and Euclidean Distance.
- Criterion functions: Calinski-Harabasz and Davies-Bouldin
- Algorithms: K-Means and Hierarchical Clustering
- Feature extraction techniques: Term Frequency-Inverse Document Frequency (TF-IDF) and Latent Dirichlet Allocation (LDA).

##### Working

Involves data preprocessing, feature extraction, and similarity measurement. The goal of these stages is to transform raw text data into numerical representations that can be processed and analyzed by machine learning algorithms.

![[Pasted image 20230907212014.png]]
##### Applications
Sentiment Analysis, Topic Modelling, Fake news identification