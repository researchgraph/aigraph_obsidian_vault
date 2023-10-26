https://doi.org/10.1007/s10852-005-9022-1
# Clustering Rules:  A Comparison of Partitioning and Hierarchical Clustering Algorithms

1. Summary of the paper:
	The article explores the clustering of rules in data mining and presents various clustering algorithms for this purpose. It discusses the concept of "simple rules" and describes the algorithmsthe (Fall-rules algorithm and multi-objective metaheuristics) used to generate them. Next, the paper compares different clustering techniques and evaluates their performance. The paper conducts very detailed experiments, and provides explanations for most of the experimental phenomena. One distinct deficiency is that the experiments conducted are more focused on comparing within the same type of algorithm, in other words, there is not much comparison about clustering algorithm between partitioning-based and hierarchical.
    
2. Clustering algorithm used:
	The paper mentions four partition-based clustering algorithms: k-means, k-medoids, partitioning around medoids (PAM), and a variant of PAM -- CLARANS, and finally a hierarchical clustering: agglomerative nesting (AGNES). The k-means is found to be unsuitable for rule clustering, so the paper doesn't analyze it or compare with others. And for CLARANS, it was run with three different values of a parameter 'maxneighbour', 100, 1000, 10000. And there are also two variants of CLARANS that have been discussed in the paper.
    
3. Comparison of different clustering algorithm:
	The paper uses four measures to compare different clustering algorithms: 
	- Time takens with different number of clusters.
	- Sum of distances of rules to the closest medoids with different number of clusters.
	- Sum of distances over time with a specific number of clusters.
	- Average silhouette width with different number of clusters.
	 The results show:
	- K-medoids runs super fast than other partition-based clustering algorithms.
	- The best number of clusters suggested by k-medoids based on average silhouette width does not result in a simplified view of the data. 
	- According to the sum of distances of rules to the closest medoids, PAM outperforms k-medoids except some few cases, if PAM is given enough time. The larger 'maxneighbour', the better CLARANS performs. In addition, CLARANS(100) works worst among all partition-based clustering algorithms. CLARANS(1000) and CLARANS(10000) easily outperform k-medoids, only outperforms PAM at some few numbers of clusters.
	- PAM takes a long while to reach reasonable solutions, while CLARANS is faster than PAM to find a not bad solution but it is more likely to be a 'local optimum'. The two variants of CLARANS have overwhelming advantage, combining speed and quality.
	- AGNES has the highest average silhouette width.
    
4. Deficiencies of the paper:
	- Not much comparison about clustering algorithm between partitioning-based and hierarchical.
	- Do not give the reason why AGNES has a improved average silhouette width.
	- The data of time takens of CLARANS and AGNES is not provided.