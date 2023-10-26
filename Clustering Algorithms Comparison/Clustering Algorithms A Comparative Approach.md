[https://arxiv.org/abs/1612.08388](https://arxiv.org/abs/1612.08388)

#Metrics #Comparison
## Research Objectives
- **Aim 1**: Perform a systematic comparison of 9 well-known clustering algorithms in R, assuming normally distributed data.
- **Aim 2**: Evaluate the sensitivity of these clustering algorithms in relation to their parameter configurations.

## Clustering Methods
The clustering algorithms evaluated are:
- k-means
- clara
- hierarchical
- EM
- hcmodel
- spectral
- subspace
- optics
- dbscan

## Evaluation Metrics
The paper employs the following clustering quality metrics:
- Adjusted Rand
- Jaccard
- Normalized Mutual Information
- Fowlkes Mallows

## Experimental Results
- The study uses 400 artificial datasets with tunable properties.
1. **Spectral Approach**: Tended to outperform others when using default settings.
2. **Parameter Sensitivity**: Default configurations are not always ideal, and random parameter selection can sometimes improve performance.

## Conclusions and Issues
- The paper offers a comparative study of 9 popular clustering algorithms.
- It explores the effect of parameter settings on clustering quality.
- It identifies key influencing factors for selecting an appropriate clustering method.
- The study serves as a valuable resource for selecting a clustering algorithm based on specific needs and metrics.

### Note on Fowlkes Mallows Index
Fowlkes Mallows index is an attractive metric especially when comparing the results of two clustering algorithms. It is defined as:
![[Pasted image 20230904123805.png]]
Where:
- TP: True Positives
- FP: False Positives
- FN: False Negatives

#### Difference between F-measure and FM index
- F-measure is the harmonic mean of precision and recall.
- Fowlkes-Mallows index is the geometric mean of precision and recall.

[Further Reading](https://datascience.stackexchange.com/questions/36817/why-is-the-f-measure-preferred-for-classification-tasks)

