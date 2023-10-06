
[https://doi.org/10.3389/fsoc.2022.886498](https://doi.org/10.3389/fsoc.2022.886498)

Social media posts are text heavy and unstructured, making it complicated for data analysis. But they portray human behavior and interactions and social scientists use data mining, NLP and machine learning approaches to get a better sense of them. Topic modelling can be used to analyze the data, but the validity and quality of findings are questionable. 

#### Problems faced when trying to analyze social media posts:

- Shorter posts typically lead to a higher engagement rate. But these short and unstructured posts increase the complexity for algorithms to make sense of digital interaction. 
- Common challenges arise from using compound words, acronyms, and ungrammatical sentences. Despite the productive and unexpressed nature of compound words they often complicate computational analysis 
-  Other difficulties emerge when data are meaningless (i.e., noisy data) or when there are many gaps present in the data

**Aim** : To take Twitter posts as the reference point and assess the performance of different algorithms concerning their strengths and weaknesses in a social science context.
The chosen algorithms:
(1) [[Latent Dirichlet Allocation]] (2) NMF (3) Top2Vec (4) BERTopic

**Results**

#### LDA versus NMF

- LDA and NMF had common themes. 
- Although both models refer to the chance to reunite with their loved ones, LDA, in particular, points out how the COVID-19 pandemic has influenced the Diversity Visa Program application.
- While both models disclose Twitter users' opinions on travel ban restrictions and quarantine, the LDA results appear to be more geographically oriented. LDA reveals issues surrounding the Australian border.
- But LDA also produced more universal and irrelevant topics that barely offer any meaningful implications.
 
 Due to a clear distinction between all the identified topics in the NMF model, its results are more in line with human judgment, thereby outperforming LDA in general.

#### BERTopic versus Word2Vec

By relying on an embedding model, BERTopic and Top2Vec require an interactive process for topic inspection.
- Both algorithms discover highly relevant topics revolving around a specific term for a more in-depth understanding.
- For the theme "travel bubble" both algorithms produced five relevant topics. In this case, the BERTopic results seem to be more specific, with a clear distinction on travel between countries. Other issues center on travel passes and business travel. With regards to Top2Vec, however, the results revealed a slight overlap. For example, the travel bubble between Australia and New Zealand is covered in four out of five topics; similarly, Singapore, Hong Kong, and Taiwan are also mentioned several times.
- In addition, Top2Vec produces topics with multiple aspects. One topic covered issues related to 6 different countries. 

#### Overall

- Both BERTopic and NMF provide a clear cut between any identified topics, the results obtained from NMF can still be considered relatively “standard.” 
- In addition to the expected topics, BERTopic was able to generate novel insights using its embedding approach. 
- Although Top2Vec also uses pretrained embedding models, the results cover more topics that overlap and contain multiple concepts
- The topics produced by LDA do not seem to be very intriguing. 
- Despite some Top2Vec topics appearing as irrelevant and difficult to understand, the model, is capable of producing a few interesting findings rarely mentioned by other algorithms.
- As a result, in favor of extracting novel conclusions, Top2Vec is recommended over LDA.
#### The advantages and disadvantages of the algorithms:

![[Pasted image 20230912174355.png]]





