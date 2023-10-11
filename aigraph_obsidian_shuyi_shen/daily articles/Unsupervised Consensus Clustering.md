[Unsupervised Consensus Clustering | Eni digiTALKS (medium.com)](https://medium.com/eni-digitalks/unsupervised-consensus-clustering-316bc904707c)

#consensus #clustring 

**Consensus clustering** is a Machine Learning method that combines the results of multiple clustering algorithms to produce a more robust and reliable clustering solution.

### How it works
CC works by aggregating the results of multiple clustering runs into a consensus matrix, which is a matrix that summarizes the similarity between pairs of data points across all clustering solutions.

### Pros 

- **Robustness**: Consensus Clustering can provide more robust results than single clustering algorithms. By combining the results of multiple algorithms, CC reduces the impact of noise in the data and arbitrary choices, producing more stable and reliable clustering solutions.
- **Improved accuracy**: By exploring multiple algorithms, CC can also improve the accuracy of the final solution. This is because different algorithms can capture different structures in the data, and CC allows these structures to be combined into a more robust single solution.
- **Flexibility**: CC can be useful in situations where it is not clear which algorithm is best suited for a particular dataset. By comparing different unsupervised methods, it can provide a way to find the best solution for a particular problem.

### Cons

- **Computational cost**: CC can be computationally expensive, as it requires running multiple ML instances and comparing their results. This can make consensus clustering impractical for very large datasets or for problems with strict time constraints.
- **Algorithm selection**: Choosing the right set of clustering algorithms to use can be challenging. It is important to select algorithms that are appropriate for the problem and dataset, as well as algorithms that are likely to produce complementary results.
- **Interpreting results**: The final result of consensus clustering can be harder to interpret than the results from a single algorithm. This is because the final solution is a combination of outputs, which can make it difficult to understand the underlying structures in the data and the decisional process.
- **Misleading results**: In some cases, this method can produce false results. CC might produce well separated clusters in the latent space even if the point within the clusters is not intrinsically related. It can forcefully find stable results when there really isn’t any relation between data points.