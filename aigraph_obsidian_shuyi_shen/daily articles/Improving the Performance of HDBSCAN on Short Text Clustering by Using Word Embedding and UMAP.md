[Improving the Performance of HDBSCAN on Short Text Clustering by Using Word Embedding and UMAP | IEEE Conference Publication | IEEE Xplore](https://ieeexplore.ieee.org/document/9640285)

#HDBSCAN #Short-Text #improvement 

Problem: [[Density-Based Clustering -  DBSCAN vs. HDBSCAN|HDBSCAN]] is bad at clustering high-dimensional data.
Solution: Use dimensionality reduction algorithm, specifically UMAP.
Reason: UMAP has the ability to preserve density information better than other similar algorithms.

Comparison:

| Model | Purity | NMI |
| --- | --- | --- |
| FastText+UMAP+HDBSCAN | 0.895 | 0.867 |
| FastText+HDBSCAN | 0.409 | 0.458 |
| BERT+UMAP+HDBSCAN | 0.868 | 0.850 |
| BERT+HDBSCAN | 0.560 | 0.623 |
| TFIDF+UMAP+HDBSCAN | 0.868 | 0.818 |
| TFIDF+HDBSCAN | 0.447 | 0.505 |



| Model | Accuracy | F1-Score |
| --- | --- | --- |
| FastText+UMAP+HDBSCAN | 0.915 | 0.901 |
| FastText+HDBSCAN | 0.894 | 0.885 |
| BERT+UMAP+HDBSCAN | 0.917 | 0.904 |
| BERT+HDBSCAN | 0.898 | 0.888 |
| TFIDF+UMAP+HDBSCAN | 0.897 | 0.889 |
| TFIDF+HDBSCAN | 0.894 | 0.885 |
