[https://medium.com/analytics-vidhya/comparative-study-of-the-clustering-algorithms-54d1ed9ea732](https://medium.com/@swansburg.justin/how-to-use-llms-to-build-better-clustering-models-9b17a5491bb4)

Rather than one-hot encode or standardize the input features, a single text string can be created for each row in the dataset and run through an [[Large Language Models|LLM]] to get back an embedding. Embedding approach produces more separated clusters.

Sentence transformers are LLMs that work similar to BERT, except that it’s specially trained to output embeddings at the sentence level rather than the word or token level. These sentence level embeddings do a better job of capturing meaning and are far quicker to compute.

