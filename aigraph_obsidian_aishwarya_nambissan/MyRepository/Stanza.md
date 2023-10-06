[https://doi.org/10.48550/arXiv.2003.07082]

Stanza is an open-source Python natural language processing toolkit. 
Stanza features a language-agnostic fully neural pipeline for text analysis, including tokenization, multiword token expansion, [[Stemming and Lemmatization#Lemmatization|lemmatization]], part-of speech 
and morphological feature tagging, dependency parsing, and named entity recognition.

### Problems with existing toolkits:

1. Only support a few major languages, making it difficult to process multilingual text.
2. Accuracy is not always achieved since  efficiency is prioritized potentially leading to misleading insights obtained from the processing.
3.  Some tools assume input text has been tokenized or annotated with other tools, lacking the ability to process raw text within a unified framework.

### Advantages of Stanza:

From raw text to annotations - Produces annotations from raw text including tokenization, multi-word token expansion etc.

Multilinguality - Supports 66 languages

State-of-the-art performance - The neural pipeline adapts well to texts from different genres.

#### Architecture
(1) a fully neural multilingual [[Natural Language Processing|NLP]] pipeline
(2) a Python client interface to the Java Stanford CoreNLP software

The implementation of Stanza components is highly modular, and reuses basic model architectures for compactness.