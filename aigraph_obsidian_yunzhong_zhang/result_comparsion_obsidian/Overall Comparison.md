Mainly discuss the result below: 
- Topics produced by four models(HDBSCAN, GMM, LDA, NMF)
- Documents distribution of clusters produced by four models
- Keywords occurrences of  the common clusters(which keywords contribute to the cluster)

Note: HDBSCAN, GMM and LDA use the same preprocess, and all of four use the same stop words. 

## Topics

|HDBSCAN#topic=10|GMM#topic=15|LDA#topic=12|NMF#topic=14|
|---|---|---|---|
|Education|Education|Education|Education|
|Medical|Medical|Medical|Medical|
|Cyber-security|Cyber-security|Cyber-security|Cyber-security|
|Non-sense|Non-sense|Non-sense|non-sense|
|NLP|NLP|NLP|-|
|CV|CV|-|CV|
|-|society|society|society|
|-|industry|industry|industry|
|Biology|biology|-|-|
|Math|-|-|Math|
|Ecosystem|Ecosystem|-|-|
|-|robot|robot|-|
|-|engineering|engineering|engineering|
|-|neuron-science|neuron-science|-|
|-|-|IoT|IoT|
|reinforcement-learning|-|-|reinforcement-learning|
|voice|recommendation-system|research|machine learning|
|-|quantum|game|decision tree|
|-|-|-|disease|

Notice: - means this model doesnot produce the topic. 


## Cluster distribution

![[distribution_overall.png]]


Direct to the folds named by the algorithms for more details. 

## Keywords occurrences of Common topics
![[occurance_cyber-security_comp.png]]

![[occurance_education_comp.png]]

![[occurance_medicine_comp.png]]

![[occurance_nonsense_comp.png]]