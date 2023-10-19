https://journals.plos.org/plosone/article?id=10.1371/journal.pone.0018029

#criteria #clustering #evaluation #PMRA #BM25

The paper compare five clustering model

- tf-idf
    
- LSA

- topic modeling
    
- BM25
    
- PMRA
    

applying on two features of "Two Million Biomedical Publications" dataset

- MeSH subject headings and
    
- titles&abstract,
    

based upon two metric to evaluate the clustering performance

- within-cluster textual coherence, which is actually based upon the word frequency distribution difference between single document and the cluster that it belongs to.
    
- recall and precision based upon grant-to-article, which based on the assumption that the articles acknowledging a single grant should be highly related,
    

It is noticed that the dataset is "Two Million Biomedical Publications", so the metric used in article, especially the "grant-to-article", which use sponsors as the label, to evaluate the clustering performance, might be potential metric that can be used to validate our AI-article clustering results.

## Summary

The paper focus on the biomedical publications, introduce and compare 5 clustering techniques on 2 million biodemdical publicans. The clustering performance is evaluated by two metrics, one is "within-cluster textual coherence", which based on word frequency, another is "grant-to-article", which consider the papers granted by the same department are highly related, or in the same cluster. In experiments, PMRA and BM25 demonstrates significantly better performance on both of the metric above. These two might be good models in publications clustering. (So might works well on our AI-articles scenario). What makes me impressive is the metric "grant-to-article" used to validate the clustering results. It automatically label the publications by its grant, which might be a good method in researching publications. But whether the label reliable is unknown, it might need to further verified and improve. Also, as for the "textual coherence", its actually a biased measure since the validation inputs and clustering inputs are highly overlapped.