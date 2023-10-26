[https://doi.org/10.48550/arXiv.1707.02268](https://doi.org/10.48550/arXiv.1707.02268)


Automatic text summarization is the task of producing a concise and fluent summary while preserving key information content and overall meaning. It is challenging since computers lack human knowledge and language capability, it doesn't understand an entire piece of text like humans do.

Earlier automatic summarization techniques used _word and phrase frequency_ which proposed to weight the sentences of a document as a function of high frequency words, ignoring very high frequency common words.

To calculate sentence weights:
1. Cue Method - Relevance is calculated based on the presence or absence of certain cue words in the cue dictionary
2. Title Method: The weight of a sentence is computed as the sum of all the content words appearing in the title and headings of a text.
3.  Location Method: This method assumes that sentences appearing in the beginning of document as well as the beginning of individual paragraphs have a higher probability of being relevant.

2 approaches for Automatic Text Summarization:
- Extraction - Identifies important sections of the text and generates the summary verbatim
- Abstraction - Uses advanced NLP techniques to generate a new shorter text that conveys the most critical information from the original text

Purely extractive summaries often times give better results compared to automatic abstractive summaries. This is because abstractive summarization
methods cope with problems such as semantic representation, inference and natural language generation which are relatively harder than data-driven approaches such as sentence extraction.

Steps for Extractive summarization:
1. Intermediate representation
	2 approaches:
		_Topic representation_ - Transforms the text to topics for interpretation
		_Indicator representation_ - Describes every sentence as a list of features (indicators) of importance such as sentence length, position in the document, having certain phrases etc
1. Score the sentences based on the representation - An importance score which indicates how well the sentence explains the most important topics of the text is assigned to each sentence of the intermediate representation
2. Select a summary comprising of a number of sentences - summarizer system selects the top k most important sentences to produce a summary using greedy algorithms or optimization problem approaches.

#### Topic Representation

##### Topic Words
Aims to identify words that describe the topic of the input document.
_Topic Signature_ :  When log likelihood ratio test is used to identify explanatory words by using frequency thresholds to locate the descriptive words that represent the topic of the document.

Two ways to compute the importance of a sentence:
1. As a function of the number of topic signatures it contains -> Longer sentences may have higher scores since they have more words
2. As the proportion of the topic signatures in the sentence -> measures the density of the topic words

##### Frequency driven approaches
Common techniques : Word probability, TF-IDF

Word probability : Number of occurrences of the word divided by the number of all the words in the input.

[[A Novel Text Mining Approach Based on TF-IDF and Support Vector Machine for News Classification#TF-IDF|TF-IDF]] - Assesses the importance of words and identifies very common words that should be omitted from consideration in the document by giving low weights to words appearing in  most documents.

Latent Semantic Analysis : Unsupervised method for extracting a representation of text semantics based on observed words.

Bayesian Topic Models : Probabilistic models that uncover and represent the topics of documents. They are quite powerful and appealing, because they represent the topics that are lost in other approaches.

#### Knowledge Bases and Automatic Summarization

Combines summarization techniques with knowledge bases. By considering the ontology features, the semantic representation of sentences are improved which is beneficial in selection of sentences for summaries. Ontology-based extraction of sentences
outperforms baseline summarizers.

Web Summarization
Web pages contain pictures which cannot be summarized. To overcome this, pieces of information extracted from the content of all pages linking to it are used as additional material to improve summarization.

Scientific Articles Summarization
Based on citation

Email Summarization
Scientific techniques must consider that there will be both conversation and written text. Summary in this case is generated from the first 2 levels of thread discussion.

#### Indicator Representation Approaches
Models the representation of text based on a set of features and use them directly to rank the sentences.

Graph Method
Graph methods are influenced by PageRank algorithm and represent the documents as a connected graph. Sentences form the vertices of the graph and edges between the sentences indicate how similar the two sentences are.

Machine Learning for Summarization
Models the summarization as a [[Classification|classification]] problem


#### Evaluation
1. Human evaluation 
2. Automatic Evaluation - ROUGE - Recall-Oriented Understudy for Gisting Evaluation (ROUGE) to automatically determine the quality of a summary by comparing it to human summaries.