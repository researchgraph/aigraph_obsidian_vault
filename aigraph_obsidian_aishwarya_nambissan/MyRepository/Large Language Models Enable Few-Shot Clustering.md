
[https://doi.org/10.48550/arXiv.2307.00524](https://doi.org/10.48550/arXiv.2307.00524)

[[Supervised versus unsupervised learning#Semi supervised learning|Semi-supervised ]]clustering enables the domain expert to guide the clustering algorithm, making the [[Clustering|clustering]] more streamlined and useful for the users.

But, this interaction between an expert and a clustering algorithm can be expensive, require significant effort from the experts and they have the control over the final clusters.

**Aim** - Explore three places in the [[Clustering#Text Clustering|text clustering]] process where an [[Large Language Models|LLM]] could be leveraged: (1) before clustering
(2) during clustering
(3) after clustering
to see if they can direct the clustering algorithm, thus requiring less input from the experts

Before clustering -  augmenting the textual representation. That is, before any cluster is produced, experts typically know what aspects of each document they wish to capture during clustering. Instead of forcing clustering algorithms to mine such key factors from
scratch, it could be valuable to globally highlight these aspects beforehand by generating key phrases with an LLM and then encoding these phrases to add them to the base representation.

During clustering - by adding cluster constraints by using an LLM as a pairwise constraint pseudo oracle such that it selects pairs of points which must be linked or cannot be
linked so that more abstract clustering needs of experts can be implicitly induced from the concrete feedback.

After clustering -  by correcting low-confidence cluster assignments using the pairwise constraint pseudo-oracle. 

In every case, the interaction between a user and the clustering algorithm is enabled
by a prompt written by the user and provided to a large language model.

Evaluation Metrics : Normalized Mutual Information, 

Results 

- Compared to traditional [[K-means clustering]]  on document embeddings, using an LLM to enrich each document’s representation improves cluster quality on every metric for all datasets  considered. 
- Using an LLM as a pairwise constraint pseudo-oracle can also be highly effective when the LLM is capable of providing pairwise similarity judgements but requires a larger number of LLM queries to be effective.
- However, LLM post-correction provides limited upside. 
- LLMs can also approach the performance of traditional semi-supervised clustering with a human oracle at a fraction of the cost.