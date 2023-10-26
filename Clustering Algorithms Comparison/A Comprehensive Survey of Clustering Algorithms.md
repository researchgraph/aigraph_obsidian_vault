# A Comprehensive Survey of Clustering Algorithms

### 1. Summary of the paper:
The paper mainly introduces the basic and core idea of commonly used clustering algorithms, and their strengths and weaknesses. Although the algorithm theories are not detailed enough, the paper provides references for each algorithm for people who intend to study further. What makes this paper distinctive is that it analyzes the clustering algorithms from two perspectives, from traditional to modern ones. Finally the paper provides a comprehensive comparisons of all algorithms mentioned, which are quite convenient for practitioners and researchers to choose suitable clustering algorithms.
### 2. Taxonomy of clustering algorithms:
The paper provides two different taxonomies for traditional and modern clustering algorithms respectively. There are several typical algorithms under each category. Some algorithms may overlap.

Traditional algorithms:
	![[501bef75c85692ea55866f7a7835745.png]]

Modern algorithms:![[70172c3004be6012f346a19a7bb6d05.png]]



### 3. Comparisons:
- **Low time complexity**: K-means, BIRCH, CURE, FCM, CLICK, STING, CLIQUE, FC, COBWEB, Wavecluster,  STREAM, CluStream.
- **High scalability**: CLARA, BIRCH, CURE, Chameleon, GMM, CLICK, MST, STING, CLIQUE, FC, ART, kernel SOM, Wavecluster, CluStream, HPStream, DenStream.
- **For large-scale data**: K-means, CLARA, CLARANS, BIRCH, CURE, DBCLASD, DBSCAN, OPTICS, CLICK, MST, STING, FC, COBWEB, ART, Wavecluster, STREAM, CluStream, HPStream, DenStream, DENCLUE.
- **For high dimensional data**: CURE, ROCK, DBCLASD, STING, CLIQUE, FC, SOM, SM, NJW, HPStream, DENCLUE.
- **Arbitrary shape of data set**: CURE, ROCK, Chameleon, FCS, MM, DBCLASD, GMM, DBSCAN, OPTICS, Mean-shift, CLICK, MST, STING, FC, COBWEB, SOM, ART, kernel K-means, kernel SOM, kernel FCM,  SVC, MMC, MKC, ACO_based, PSO_based, SFLA_based, ABC_based, SM, NJW, DD, Wavecluster, DenStream, DENCLUE.
- **Little sensitive to the sequence of inputting data**:  DBCLASD, OPTICS, Mean-shift, STING, CLIQUE, COBWEB, SOM, kernel SOM, SVC, MMC, MKC, ACO_based, QC, DQC, SM, NJW, DD, Wavecluster.
- **Little sensitive to noise/outlier**: K-medoids, PAM, CLARA, CLARANS, BIRCH, CURE, ROCK, Chameleon, MM, DBCLASD, GMM, DBSCAN, OPTICS, Mean-shift, STING, FC, SOM, kernel K-means, kernel SOM, kernel FCM, SVC, MMC, MKC, QC, DQC, SM, NJW, AP, DD, DenStream, DENCLUE.

- **Satisfy all properties**: STING

STING is a clustering algorithm based on grid. The core idea of STING which can be used for parallel processing is that the data space is divided into many rectangular units by constructing the hierarchical structure and the data within different structure levels is clustered respectively. The advantages are low time complexity, high scalability and suitable for parallel processing and increment updating. And disadvantages are the clustering result sensitive to the granularity (the mesh size), the high calculation efficiency at the cost of reducing the quality of clusters and reducing the clustering accuracy.