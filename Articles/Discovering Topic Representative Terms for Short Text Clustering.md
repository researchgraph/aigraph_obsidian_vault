[https://doi.org/10.1109/ACCESS.2019.2927345](https://doi.org/10.1109/ACCESS.2019.2927345)

- Short texts on the same topic often have common terms, which are called topic representative terms. 

- Topic representative terms discovery(TRTD) method  focuses on their closeness and significance. Closeness is measured by how often the terms co-occur, while significance is measured by their global occurrences in the entire text corpus. 

- Short text [[Clustering]] is challenging due to features like abbreviations and informal expressions, which result in sparse, noisy, and high-dimensional data.
- Existing short text clustering methods can be categorized as representation-based or model-based. Representation-based methods use enriched or compact features to overcome sparsity issues, followed by applying conventional clustering techniques like  K-Means.
- The topic representative terms discovery (TRTD) method involves
	1. constructing a node/edge-weighted word graph
	2. extracting representative term groups
	3. Clustering short texts. 

TRTD constructs a graph that aggregates word statistics from the entire corpus to alleviate sparsity issues. Seed terms with higher weights are identified, and their closely related neighbor terms form topic representative term groups for short text clusters. Finally, the most similar topic representative term group is used to cluster short texts. TRTD yields more accurate representative terms while filtering out trivial terms.