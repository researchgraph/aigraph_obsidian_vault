[https://www.techtarget.com/whatis/definition/large-language-model-LLM](https://www.techtarget.com/whatis/definition/large-language-model-LLM)

A language model provides a basis to communicate and generate new concepts.

A large language model (LLM) is a type of [[Artificial Intelligence | artificial intelligence]] algorithm that uses [[Machine learning and deep learning | deep learning]] techniques and _massively large data sets_ to understand, summarize, generate and predict new content. 

All language models are first trained on a set of data, and then they make use of various techniques to infer relationships and then generate new content based on the trained data.

Modern LLMs emerged in 2017 and use transformer neural networks, commonly referred to as _transformers_ and about a billion parameters. 

#### Foundation models 
Some LLMs are so large and impactful that it serves as the foundation for further optimizations and specific use cases.
#### Working

- Usually uses [[Supervised versus unsupervised learning#Unsupervised learning | unsupervised learning]] to be trained on a large corpus to derive relationships between words and concepts
- Fine tuning with [[Articles/A very gentle introduction to large language models without the hype#Self supervised|self supervised learning]] and data labelling to accurately identify different concepts
- Undertakes deep learning as it goes through the transformer neural network process. The transformer architecture enables the LLM to understand and recognize the relationships and connections between words and concepts using a self-attention mechanism. That mechanism is able to assign a score, commonly referred to as a _weight_, to a given item (called a _token_) in order to determine the relationship.
- Once an LLM has been trained, a base exists on which the AI can be used for practical purposes. By querying the LLM with a prompt, the AI model inference can generate a response, which could be an answer to a question, newly generated text, summarized text or a sentiment analysis
#### Applications
Text generation, translation, content summary, rewriting content, classification and categorization, sentiment analysis, chatbots etc
#### Advantages
- **Extensibility and adaptability.** LLMs can serve as a foundation for customized use cases. Additional training on top of an LLM can create a finely tuned model for an organization's specific needs.
- **Flexibility.** One LLM can be used for many different tasks and deployed across organizations, users and applications.
- **Performance.** Modern LLMs are typically high-performing, with the ability to generate rapid, low-latency responses.
- **Accuracy.** As the number of parameters and the volume of trained data grow in an LLM, the transformer model is able to deliver increasing levels of accuracy.
- **Ease of training.** Many LLMs are trained on unlabeled data, which helps to accelerate the training process.

#### Limitations
- **Development costs.** To run, LLMs generally require large quantities of expensive graphics processing unit hardware and massive data sets.
- **Operational costs.** After the training and development period, the cost of operating an LLM for the host organization can be very high.
- **Bias.** A risk with any AI trained on unlabeled data is bias, as it's not always clear that known bias has been removed.
- **Explainability.** The ability to explain how an LLM was able to generate a specific result is not easy or obvious for users.
- **Hallucination.** AI hallucination occurs when an LLM provides an inaccurate response that is not based on trained data.
- **Complexity.** With billions of parameters, modern LLMs are exceptionally complicated technologies that can be particularly complex to troubleshoot.
- **Glitch tokens.** Maliciously designed prompts that cause an LLM to malfunction, known as _glitch tokens_, are part of an emerging trend since 2022.
#### Types
- **Zero-shot model.** This is a large, generalized model trained on a generic corpus of data that is able to give a fairly accurate result for general use cases, without the need for additional training. 
		Eg: GPT-3 is often considered a zero-shot model.
- **Fine-tuned or domain-specific models.** Additional training on top of a zero-shot model like GPT-3 can lead to a fine-tuned, domain-specific model. 
		Eg: OpenAI Codex
- **Language representation model.** Makes use of deep learning and transformers well suited for NLP.
		Eg: BERT
- **Multimodal model.** Originally LLMs were specifically tuned just for text, but with the multimodal approach it is possible to handle both text and images.
		Eg: GPT-4
