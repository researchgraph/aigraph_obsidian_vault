https://ieeexplore.ieee.org/document/9215004

- Many current [[Clustering#Text Clustering|text clustering]] algorithms rely on the bag-of-words model, which suffers from issues like high dimensions, sparsity, and disregards text structure and sequence details.
- Deep learning models like convolutional and recurrent neural networks consider texts as sequences but lack supervision and interpretable outcomes. 
-  Several text-feature enhancement models are available for text clustering. A similarity metric for text clustering to capture the structural information of texts, applying a concept knowledge base to extend text features and thus enhancing the semantics of the representation are some of the models. But these are still based on feature space models and thus cannot solve the problem of poor semantic understanding.
- Model-based clustering algorithms that view the clustering process as a generative model like [[Latent Dirichlet Allocation|LDA]] and  collapsed Gibbs sampling algorithm for the Dirichlet multinomial mixture model (GSDMM) consider only the words in the current text and ignore all irrelevant words in the vocabulary. Hence, a generative model avoids the processing of high-dimensional and sparse feature matrices.

**AIM** : To introduce a novel approach called deep feature-based text clustering (DFTC), which integrates pre-trained text encoders into text clustering tasks.

**WHY** : In contrast to the bag-of-words model, the pretrained deep text encoder directly processes text word by word and provides a semantic representation. Moreover, the pretrained deep text encoder solves the feature sparsity problem.

**FRAMEWORK** : 
- For each text a pretrained text encoder is used to extract features. 
- Two pretrained deep text encoders, namely, the language model and the language inference model _InferSent_, both of which are based on LSTM(long short-term memory networks) are used. 
- In the second step, a feature normalization module employs normalization techniques (e.g., layer normalization) to ensure the features’ numerical stability and to ensure that the feature vectors satisfy specific qualities, such as conforming to a normal distribution. 
- In the last step, the normalized features are fed into the selected clustering algorithm, such as K-means. After obtaining the cluster partition results, the explanation model produces representative words for each cluster.

**EVALUATION METRICS:**
Clustering accuracy (ACC) , normalized mutual information (NMI), and adjusted Rand index (ARI)

Most neural language models are built from an LSTM network and are trained to predict the next word given the previous words. However, due to the unstable gradient problem of LSTM, a backward language model can supplement the complementary information neglected by the forward language model. In contrast to forward language models, backward language models predict the previous word given the following words.

**THE EXPLANATION MODEL : TCRE**

Inputs : The corpus and clustering results

Main idea : Every text in a given corpus is labeled with a class ID given the clustering results, and these labels can be regarded as pseudolabels of the texts. A logistic classifier is then used to fit the associations between texts and pseudolabels

Working :
1. The _TCRE_ model maps the text in the corpus into bag-of-words features. In contrast to ordinary text classification, 0-1 features are the inputs of the classifier instead of tf-idf features. If a word exists in a text, the feature value of the word is 1; otherwise, the feature value is 0
2. The _TCRE_ model acquires indication words that express every cluster’s meaning using logistic regression classifier. The higher the score of a word in a cluster, the more important that word is in the cluster. For each cluster, the _TCRE_ model selects the top n words with the highest scores as indication words which can be used to measure the quality of clustering and to understand the semantics of the cluster partition.




