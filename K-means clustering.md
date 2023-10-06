[https://towardsdatascience.com/understanding-k-means-clustering-in-machine-learning-6a6e67336aa1](https://towardsdatascience.com/understanding-k-means-clustering-in-machine-learning-6a6e67336aa1)

https://www.mdpi.com/2571-8800/2/2/16

https://towardsdatascience.com/how-many-clusters-6b3f220f0ef5

Objective : Group similar data points together into a fixed number of clusters and discover underlying patterns

Cluster : Collection of datapoints aggregated together due to similarities

Centroid : Imaginary or real location indicating the center of the cluster

Allocation of datapoints is done by reducing the in-cluster sum of squares

means in k-means refers to averaging the data, that is, finding the centroid

In data mining, the K-means algorithm starts by selecting random centroids as the initial points for each cluster. It then continues to make calculations and adjust the positions of the centroids through several iterations to find the optimal clusters. The algorithm stops when either the centroids' values remain constant, indicating successful clustering, or when the specified number of iterations is reached.

k-means is easy to use and delivers training results quickly but slight variations in data could lead to high variance in results. Also, clusters are assumed to be spherical which could reduce the accuracy.

The objective of clustering is to divide data points into clusters where (1) the similarity between points within the same cluster is maximized and (2) points belonging to different clusters are as dissimilar as possible. In other words, ideal clustering aims to minimize the variation within clusters while maximizing the variation between clusters.

#### Inertia :  
Calculated as the sum of squared distances between data points and the centers of the clusters they belong to. Inertia quantifies the within-cluster variation.

#### Silhouette Coefficient: 
Attempts to summarize both within-cluster and between-cluster variation. At each data point, the distance to the cluster center in which the data point belongs (referred to as a) is calculated, as well as the distance to the second best cluster center (referred to as b). The second best cluster refers to the closest cluster that is not the current data point’s cluster. Then based, on these two distances a and b, the silhouette s of that data point is calculated as s=(b-a)/max(a,b).

Once _s_ is calculated at all data points, the average of _s_ determines a silhouette coefficient. A silhouette coefficient can be calculated for each cluster separately, or for all data points. A silhouette coefficient close to 1 indicates that a clustering algorithm is able to partition data into well-separated clusters.


For the K-means algorithm, the number of clusters depends on the K-value setting.

This k value can be determined using:

### Elbow Method

- Elbow rule is a technique used to determine the optimal number of clusters in a clustering algorithm.
- The method involves calculating the sum of squared errors (SSE), which is a measure of how close the data points are to the centroids of their respective clusters.
- The SSE is calculated for different values of K, where K represents the number of clusters.
- As the number of clusters increases, the SSE usually decreases because clusters become more compact and data points are closer to their respective centroids.
- The idea behind the elbow rule is to plot the K-SSE curve, with K on the x-axis and SSE on the y-axis, and look for an "elbow" point where the rate of decrease in SSE significantly diminishes.
- The elbow point represents the optimal number of clusters, as further increasing K does not provide substantial improvement in clustering performance.
- This method assumes that the number of real clusters is unknown and needs to be estimated.
- When K is smaller than the true number of clusters, adding more clusters will result in a significant reduction in SSE.
- However, when K exceeds the true number of clusters, adding more clusters will still decrease SSE but at a slower rate.
- The inflection point on the K-SSE curve, where the rate of decrease in SSE becomes slower, marks the turning point and corresponds to the optimal value of K.
- The elbow rule helps in making an informed decision about the appropriate number of clusters to use in the clustering algorithm.

### Silhouette Method


Objective method of finding the optimal number of clusters.

Calculate silhouette coefficient over a range of k and plot the graph. The peak of the graph gives the optimal value for k.

### Gap statistic 

 The gap statistic is calculated by comparing the inertiae from a clustered data set and a corresponding random data set covering the same ranges in the data space. The calculation of a gap statistic involves a simulation. Optimal _K_ determined by the gap statistic method may not be consistent. When the gap statistic method is applied many times, the resulting optimal _K_ may be different


#### Key takeaways

The interpretation of an elbow plot is rather subjective, both the silhouette coefficient and gap statistics methods can determine the number of clusters precisely. However, the gap statistic involves a simulation and it may not always produce the same solution.
