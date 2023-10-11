[[2203.05794] BERTopic: Neural topic modeling with a class-based TF-IDF procedure (arxiv.org)](https://arxiv.org/abs/2203.05794)

#BERTopic #TopicModeling #HDBSCAN 

Structure:
1. Convert documents into embeddings. (SentenceTransformer)
2. Reduce embedding dimensionality. (UMP)
3. Clustering ([[Density-Based Clustering -  DBSCAN vs. HDBSCAN|HDBSCAN]])
4. Topic representation (c-TF-IDF)

Evaluation:
![[7e599dafdb340c2348bcbe080bf8a2c.png]]
TC: topic coherence,   TD: topic diversity

Weaknesses:
- Single topic
- Topic representation is not contextual