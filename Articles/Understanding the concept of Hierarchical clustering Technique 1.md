[Understanding the concept of Hierarchical clustering Technique | by Chaitanya Reddy Patlolla | Towards Data Science](https://towardsdatascience.com/understanding-the-concept-of-hierarchical-clustering-technique-c6e8243758ec)

#HDBSCAN #clustring #generalConcept 

### Two types:
1. Agglomerative
Initially each data point is considered as an individual cluster. At each iteration, the similar clusters merge with other clusters until one cluster or K clusters are formed.
2. Divisive
In simple words, we can say that the Divisive Hierarchical clustering is exactly the opposite of the **Agglomerative Hierarchical clustering.** In Divisive Hierarchical clustering, we consider all the data points as a single cluster and in each iteration, we separate the data points from the cluster which are not similar. Each data point which is separated is considered as an individual cluster. In the end, we’ll be left with n clusters.

### Calculate the similarity between two clusters
- MIN
- MAX
- Group Average
- Distance Between Centroids
- Ward’s Method