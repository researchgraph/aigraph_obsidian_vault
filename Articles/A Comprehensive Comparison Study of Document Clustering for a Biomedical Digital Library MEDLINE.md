https://dl.acm.org/doi/10.1145/1141753.1141802
#Application #Comparison
## Research Objectives
- Conduct a comprehensive comparison of document clustering approaches such as:
  1. Three Hierarchical Methods
  2. Bisecting K-means
  3. K-means
  4. Suffix Tree Clustering (STC)
  
- Investigate the influence of domain ontology (MeSH) on clustering quality for MEDLINE articles.

## Clustering Methods
- **Bisecting K-means**: Two options for cluster selection
  1. Selecting the largest
  2. Selecting the least overall similarity
- **K-means**
- **Hierarchical Clustering**: Options include
  1. Single-link
  2. Complete-link
  3. UPGMA (Average-link)
- **Suffix Tree Clustering (STC)**

## Evaluation Metrics
- **Clustering Quality Metrics**
  1. Misclassification Index (MI)
  2. F-measure
  3. Purity
  4. Entropy
- **Sectional Metric**
  1. Running Time in Sec (Excluding time for word*document matrix generation)

## Experimental Results
1. Bisecting K-means' cluster selection methods affect clustering quality; Type A is superior in multiple metrics.
2. Bisecting K-means generally outperforms K-means when using cluster selection method Type A.
3. STC is better than hierarchical algorithms but worse than partitional clustering.
4. Partitional clustering approaches are superior in metrics and running time to hierarchical approaches.
5. Bisecting K-means is generally superior and requires the least time complexity.
6. MeSH ontology improves clustering quality; STC benefits the most.
7. Correlations among evaluation metrics are reported.

## Conclusions and Issues
- Partitional clustering methods are generally superior.
- Domain ontology (MeSH) improves clustering quality.
- Scalability is an issue for hierarchical algorithms.

