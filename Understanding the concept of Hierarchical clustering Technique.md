
https://towardsdatascience.com/understanding-the-concept-of-hierarchical-clustering-technique-c6e8243758ec

Two types:

[[Clustering#Hierarchical Agglomerative Clustering|Hierarchical Agglomerative Clustering]]

**Divisive Hierarchical clustering Technique:** In this technique, initially all the data points are considered as a single cluster and in each iteration, we separate the data points from the cluster which are not similar. Each data point which is separated is considered as an individual cluster. In the end, we’ll be left with n clusters.

Common Similarity measures:

- MIN (single-linkage algorithm)
	- Pick the two closest points such that one point lies in cluster one and the other point lies in cluster 2 and takes their similarity and declares it as the similarity between two clusters.
	- Pros : Can separate non-elliptical shapes as long as the gap between the two clusters is not small.
	- Cons : - Cannot separate clusters properly if there is noise between clusters.
- MAX (complete-linkage algorithm)
	- Pick the two farthest points such that one point lies in cluster one and the other point lies in cluster 2 and takes their similarity and declares it as the similarity between two clusters.
	- Pros : Does well in separating clusters if there is noise between clusters. 
	- Cons : Is biased towards globular clusters.
		      Tends to break large clusters.
- Group Average
	- Take all the pairs of points and compute their similarities and calculate the average of the similarities.
	- Pros : Does well in separating clusters if there is noise between clusters.
	- Cons : Biased towards globular clusters.
- Distance Between Centroids
	- Compute the centroids of two clusters C1 & C2 and take the similarity between the two centroids as the similarity between two clusters.
- Ward’s Method
	- This approach of calculating the similarity between two clusters is exactly the same as Group Average except that Ward’s method calculates the sum of the square of the distances between the points in cluster1 and cluster 2
	- Pros : Does well in separating clusters if there is noise between clusters.
	- Cons : Biased towards globular clusters.
	
**Space and Time Complexity of Hierarchical clustering Technique**

**Space complexity:** The space required for the Hierarchical clustering Technique is very high when the number of data points are high as we need to store the similarity matrix in the RAM.

Space complexity = O(n²) where n is the number of data points.

**Time complexity:** Since we’ve to perform n iterations and in each iteration, we need to update the similarity matrix and restore the matrix, the time complexity is also very high.

Time complexity = O(n³) where n is the number of data points.


