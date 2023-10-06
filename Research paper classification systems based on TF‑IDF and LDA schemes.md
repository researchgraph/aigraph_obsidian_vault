[https://link.springer.com/article/10.1186/s13673-019-0192-7](https://link.springer.com/article/10.1186/s13673-019-0192-7)


Finding research papers on specific topics or subjects is time consuming activity and researchers get bored when the information they are looking for is not retrieved efficiently due to the fact that the papers are not grouped in their topics or subjects for easy and fast access.

**Aim** 
To find a research paper classification system that can cluster research papers into the meaningful class in which papers are very likely to have similar subjects. 

**Proposed system** : Extracts representative keywords from the abstracts of each paper and topics by [[Latent Dirichlet Allocation]]. Then, the [[K-means clustering]] algorithm is applied to classify the whole papers into research papers with similar subjects, based on the Term frequency-inverse document frequency ([[A Novel Text Mining Approach Based on TF-IDF and Support Vector Machine for News Classification#TF-IDF | TF-IDF]]) values of each paper.

**Features** : Abstract and title of the research papers

**Dataset** : papers published on Future Generation Compute Systems (FGCS) journal from 1984 to 2017.

**Validation of clustering results** - [[K-means clustering#Silhouette Method | Silhouette scheme]]

**Procedure**
- Three kinds of keywords are used:
	- keywords that users input (Method 1),  
	- keywords extracted from abstracts (Method 2), 
	- and topics extracted by LDA scheme (Method 3).
- These keywords are used to calculate the TF-IDF of each paper, with an aim to considering an importance of papers. 
- The K-means clustering algorithm is applied to classify the papers with similar subjects, based on the TF-IDF values of each paper.
- The [[Classification]] method is designed and implemented on Hadoop Distributed File System (HDFS) to efficiently process the massive research papers that have the characteristics of big data. 
- Map-reduce programming model is used for the parallel processing of the massive research papers.

**Results**

- When topics extracted by the LDA scheme are used as keywords (Method 3), the number of clusters are less than when the other 2 options of keywords are used. 
- F-score value of Method 3 is higher than that of other methods, meaning accuracy of classification is higher. This is because the combination of TF-IDF and LDA can lead to the more detailed classification of research papers because frequently occurring keywords and the correlation between latent topics are simultaneously used to classify the papers




