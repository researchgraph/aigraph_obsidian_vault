
https://medium.com/@power.up1163/unsupervised-text-classification-with-topic-models-and-good-old-human-reasoning-da297bed7362

Labeling textual data without access to gold-standard labels is a challenge.

- Zero-shot learning is not feasible since understanding the implications of your prompt/class label choices is rather hard, and you rarely ever have a good intuition of what all of your seemingly arbitrary choices will affect.  
-  Transformers and LLMs are slow and costly. Using OpenAI’s API is expensive, and it might be impractical due to it being rather slow.

Topic models are a very reasonable compromise. Although they are not as smart as zero-shot transformer models and require a lot of manual labor to employ them in practice, they give a more fine-grained control over the process, much more interpretable results and performance benefits.


Creating a topic pipeline in topicwizard is thought of as chaining a vectorizer and a decomposition model together.

Topic modelling and using human intuition for fine tuning yields good results.
