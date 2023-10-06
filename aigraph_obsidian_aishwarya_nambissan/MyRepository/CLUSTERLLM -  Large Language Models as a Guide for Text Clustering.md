
[https://doi.org/10.48550/arXiv.2305.14871](https://doi.org/10.48550/arXiv.2305.14871)


CLUSTERLLM is a novel [[Clustering#Text Clustering |text clustering]] framework that takes feedback from an instruction-tuned large language model, such as ChatGPT to guide a small embedder for finding text clusters with low cost.

#### Advantages:
(1) It enjoys the emergent capability of LLM
(2) it understands the user’s preference on clustering through textual instruction and/or a few annotated data

#### Procedure
- The  LLMs are prompted with a triplet task that predicts which one of the two candidates is closer to the anchor instance. For instance, tasks like "Is an oval closer in shape to a circle or a square?"
- The reason a triplet task is chosen over others is that, it only needs to predict the ranking between two choices, and thus is easier for LLMs when the prior knowledge of granularity is unknown. 
- LLMs are then queried with a collection of such triplet tasks along with a task-specific instruction. 
- These instructions are used to indicate a desired perspective of clustering, such as topic, intent, emotion or even relation extraction, that is usually indicated by the user. 
- The predicted triplets thereafter are used to fine-tune small embedders with the objective function. 
- After fine-tuning, the embedding space is refined by the triplets and will produce cluster assignments according to user’s perspective.
- The most informative triplets are sampled from the dataset according to the current clustering structure since hard triplets can better benefit from the high-level language ability of LLMs. 
- For this, entropy for each instance based on cluster assignment probabilities is calculated, and then  those with highest entropy are identified.
- Two candidate choices are then sampled from its nearest clusters to guarantee that they are close enough to the anchor. 
- When a few annotated data pairs are available, the number of clusters are determined by deducing whether a pair of data belong to the same category with in-context demonstrations.
- The candidate pairs are sampled from intermediate steps of hierarchical clustering that are crucial in determining whether to split/merge clusters.
 - Finally, the decision is made by finding the best corresponded granularity in the hierarchy with the predicted pairs from LLMs.

**Embedders used** : Instructor and E5
CLUSTERLLM-E and CLUSTERLLM- I adopt E5 and Instructor as their embedders respectively. CLUSTERLLM-I-iter applies the entire framework in iterative manner for twice. All of these variants use GPT-3.5 for prediction.

#### Results

(1) Both E5 and Instructor significantly outperform GCD methods with few-shot annotations. This implies pretraining quality is especially important to discovering new categories. 
(2) Both CLUSTERLLM-E and CLUSTERLLM-I improves upon or perform similar with their original embedders consistently.