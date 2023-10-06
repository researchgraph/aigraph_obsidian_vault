
[https://doi.org/10.1007/978-981-33-4673-4_27](https://doi.org/10.1007/978-981-33-4673-4_27)


Feature extraction is one of the challenging works in the Machine Learning (ML) arena. The more features one able to extract correctly, the more accurate knowledge one can exploit from data. 

[[Latent Dirichlet Allocation]] is a form of [[Topic Modelling|topic modeling]] used to extract features from text data. But finding the optimal number of topics (on which success of LDA depends on) is tremendous challenging, especially if there is no prior knowledge about the data.

#### Normalized Absolute Perplexity (NAP) and Normalized Absolute Coherence (NAC) 

NAP is calculated by taking absolute value of Perplexity scores P$_i$  and then doing normalization. Where, P$_i$  is the perplexity score for the i$_t$$_h$ candidate value of number of topics t$_i$ . 
max(P$_i$) is the maximum value of perplexity among perplexity values for all t$_i$.

NAP=$\frac{|Pi|}{max(| Pi|)}$


NAC is calculated by taking absolute value of Coherence scores C$_i$  and then doing normalization. Where,  C$_i$  is the coherence score for the i$_t$$_h$  candidate value of number of topics t$_i$ . max( C$_i$ )is the maximum value of coherence among coherence values for all t$_i$.


NAC=$\frac{|Ci|}{max(| Ci|)}$


The higher the value of NAC, the higher the performance of the model is predicted.
The lower the value of NAP, the higher the performance of the model is predicted.

NAC and NAP perform much better than Perplexity, Coherence, and RPC. Though they do not predict the exact number of topics for which the highest accuracy can be achieved, but their predictions are much nearer than other traditional methods.