https://arxiv.org/abs/1301.7401

#EM #GMM #HAC #initialisation

## Summary

The paper focus on the comparison of algorithms to solve the same model "naive-Bayes model" on the high dimensional dataset. The model looks like generalized GMM, or say mixture model. The paper proposed memory-effcient hierarchical agglomerative clustering algorithm(HAC), essentially makes the distance computing more effcienct. It also do comparison of EM, CEM(classification EM) and HAC, based upon serval metrics that needs true information of the dataset are known. EM outperforms among these. The paper also explore the influnce of different initialization.

## Good point

- the proposed HAC ultilize the information of the algorithm, reduce the unnecessary computation.
    
- Used unsupervised classification accuracy (confusion matrix) to measure the performance. It' s quite intuitive and reasonable.
    

## Potential improvement

- the unsupervised classification accuracy used to measure the performance needs true information from the dataset, which means this can only applied on the synthetic dataset or labelled dataset.
    
- the paper only compare algorithm on high dimension on discrete-variable but didn't do it on the continous variable.