[Improving NMF clustering by leveraging contextual relationships among words - ScienceDirect](https://www.sciencedirect.com/science/article/abs/pii/S0925231222005185?via%3Dihub)

#clustring #NMF #improvement 

Limitations of [[Using Topic Modeling Methods for Short-Text Data - A Comparative Analysis|NMF]] clustering:
It does not explicitly account for the semantic relationships between words. Hence, words having a common meaning—synonyms—or more generally words that are about the same topic are not guaranteed to be mapped in the same direction in the latent space. This is simply due to the fact that words with similar meanings are not necessarily used exactly in the same documents. Consequently, similar embeddings are not guaranteed even for closely related documents using words with similar meanings. 

Solutions:
Intuitively, if we are successful in capturing the semantic relationships among words in an NMF model, we can expect document factors which are even better for clustering.
The paper introduces Semantic-NMF, a novel non-negative factorization model which explicitly accounts for the semantic relationships among words. Similar to neural word embedding techniques, our model follows the distributional hypothesis so as to leverage the relationships between words. Formally, Semantic-NMF jointly decomposes the document-word and PPMI word-context matrices, with shared word factors.