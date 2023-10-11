[[2305.14871] ClusterLLM: Large Language Models as a Guide for Text Clustering (arxiv.org)](https://arxiv.org/abs/2305.14871)

#LLM #clustring 

How does CLUSTERLLM differ from traditional unsupervised text clustering methods?

- It leverages feedback from an instruction-tuned [[What is a large language model (LLM)|large language model]], such as ChatGPT, to improve clustering quality. 
- It understands the user's preference on clustering through textual instruction and/or a few annotated data. In contrast, traditional unsupervised methods typically rely on "small" embedders and do not incorporate user feedback or annotated data.

The role of ChatGPT in CLUSTERLLM

- CLUSTERLLM constructs hard triplet questions to prompt ChatGPT for insights on clustering perspective. These questions ask whether one data point better corresponds to another data point than a third data point, where the three data points belong to different clusters according to the small embedder. 
- CLUSTERLLM uses pairwise questions to prompt ChatGPT for help on clustering granularity. These questions ask whether two data points belong to the same category, and the granularity is tuned from cluster hierarchies that are most consistent with the ChatGPT answers. By leveraging ChatGPT in this way, CLUSTERLLM is able to fine-tune the small embedder and improve clustering quality.