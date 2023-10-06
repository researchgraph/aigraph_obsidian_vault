
https://www.oreilly.com/library/view/practical-natural-language/9781492054047/ch04.html
https://www.exxactcorp.com/blog/Deep-Learning/What-is-Text-Classification

Text [[Classification]] is the task of assigning one or more categories to a given piece of text from a larger set of possible categories. This task of categorizing texts based on some properties has a wide range of applications across diverse domains, such as social media, e-commerce, healthcare, law, and marketing, to name a few.
The “text” can be of arbitrary length: a character, a word, a sentence, a paragraph, or a full document.

Text classification is sometimes also referred to as _topic classification_, _text categorization_, or _document categorization_

##### Applications
- Content classification and organization
- Customer support
- E-commerce -Sentiment Analysis

Why use machine learning text classification?

It allows for automatic analysis of large and small datasets, eliminating the need for manual data entry which is time-consuming. It also improves accuracy by reducing human errors caused by fatigue and desensitization. Additionally, the algorithm's unbiased and consistent nature increases scalability. Moreover, machine learning enables quick data access and organization, providing information in a convenient manner.

One typically follows these steps when building a text classification system:

1. Dataset: Provide a high-quality dataset, which should be labeled data, to serve as the data source for the model. When it comes to choosing and organizing a data set, Less is More, it shouldn't contain unnecessary features.
    
2. Data Filtering and Processing: Tokenize the text by splitting it into smaller units called tokens, representing words, sub-words, or characters. This step is necessary as machine learning models can only understand numerical values.
    
3. Dataset Splitting: Divide the dataset into a training set (80% of the data) and a testing set (20% of the data) to train and evaluate the model's performance.
    
4. Algorithm Training: Run the model with the training dataset to train the algorithm. The algorithm identifies patterns and insights within the text data to categorize it into different classes.
    
5. Model Testing and Performance Evaluation: Use the testing dataset (unlabeled data) to evaluate the model's performance. Compare the predicted results with the actual labels to measure the accuracy of the model.
    
6. Model Tuning: Adjust the hyperparameters of the machine learning model to optimize its performance without overfitting or creating a high variance.
    

- Hyperparameters are parameters that control the learning process of the model.
- It is important to avoid overfitting the model by testing it on new test cases that differ from the previous training data. This prevents the model from memorizing the training data and not generalizing well to new data.

Once these steps are followed, the text classification model is ready to be deployed for real-time use.
Text classification is possible without having to rely on the pipeline:

1. Lexicon based sentiment analysis: create lists of positive and negative words in English—i.e., words that have a positive or negative sentiment. We then compare the usage of positive versus negative words in the input tweet and make a prediction based on this information. Further enhancements to this approach may involve creating more sophisticated dictionaries with degrees of positive, negative, and neutral sentiment of words or formulating specific heuristics (e.g., usage of certain smileys indicate positive sentiment) and using them to make predictions. This approach is called _lexicon-based sentiment analysis_.
2. Using existing text classification APIs - APIs, such as Google Cloud Natural Language that provide off-the-shelf content classification models that can identify close to 700 different categories of text. All major service providers (e.g., Google, Microsoft, and Amazon) serve sentiment analysis APIs with varying payment structures.

## Naive Bayes Classifier
Naive Bayes is a probabilistic classifier that uses Bayes’ theorem to classify texts based on the evidence seen in training data. It estimates the conditional probability of each feature of a given text for each class based on the occurrence of that feature in that class and multiplies the probabilities of all the features of a given text to compute the final probability of classification for each class. Finally, it chooses the class with maximum probability.

 _generative classifier_
 
Class imbalance is one of the most common reasons for a classifier to not do well. We must always check if this is the case for our task and address it.

## Logistic Regression

logistic regression “learns” the weights for individual features based on how important they are to make a classification decision. The goal of logistic regression is to learn a linear separator between classes in the training data with the aim of maximizing the probability of the data. This “learning” of feature weights and probability distribution over all classes is done through a function called “logistic” function, and (hence the name) logistic regression

_discriminative classifier_

## Support Vector Machine

 It aims to look for an optimal hyperplane in a higher dimensional space, which can separate the classes in the data by a maximum possible margin. Further, SVMs are capable of learning even non-linear separations between classes, unlike logistic regression. However, they may also take longer to train.

# Using Neural Embeddings in Text Classification

 The advantage of using embedding-based features is that they create a dense, low-dimensional feature representation instead of the sparse, high-dimensional structure of BoW/TF-IDF and other such features.
 neural network–based architectures have become popular for “learning” word representations, which are known as “word embeddings.”
 An important factor to consider when deploying models with embedding-based feature extraction approaches is that the learned or pre-trained embedding models have to be stored and loaded into memory while using these approaches. If the model itself is bulky (e.g., the pre-trained model we used takes 3.6 GB), we need to factor this into our deployment needs.

fastText

They’re based on the idea of enriching word embeddings with subword-level information. Thus, the embedding representation for each word is represented as a sum of the representations of individual character n-grams. While this may seem like a longer process compared to just estimating word-level embeddings, it has two advantages:

- This approach can handle words that did not appear in training data (OOV).
    
- The implementation facilitates extremely fast learning on even very large corpora.

While fastText is a general-purpose library to learn the embeddings, it also supports off-the-shelf text classification by providing end-to-end classifier training and testing; i.e., we don’t have to handle feature extraction separately.
fastText is extremely fast to train and very useful for setting up strong baselines. The downside is the model size.

## Document Embeddings
In the Doc2vec embedding scheme, we learn a direct representation for the entire document (sentence/paragraph) rather than each word.

Text classification can be done in 2 ways:

Similarity-based approaches attempt to classify instances based on similarities between text document representations and class description representations. Zero-shot text classification approaches aim to generalize knowledge gained from a training task by assigning appropriate labels of unknown classes to text documents.

Shallow learning approaches
 - Refers to traditional machine learning methods with hand-engineered features or neural networks with few hidden layers.    

- Popular in practical contexts and serve as strong baselines.
    
- Not suitable for large datasets but effective when resources are scarce.
    
- Require costly feature engineering and domain knowledge

Deep learning approaches

- Revolutionized artificial intelligence, including text classification.
    
- Model complex features without hand engineering.
    
- Focus on developing neural network architectures to extract effective representations for text.
    
- Able to create semantically meaningful and contextual representations.
    
- Automatic feature extraction advantageous for modeling textual data, leveraging linguistic structure.


#### Tokenization approaches

##### Byte Pair Encoding

The breakthrough strategy for sub-word tokenization is known as Byte Pair Encoding (BPE). Originally developed as a compression algorithm, it was later adapted for segmenting words into sub-word units (e.g., dividing "snowboarding" into "snow", "board", and "ing"). During the tokenization process, the BPE algorithm calculates the frequency of consecutive pairs of vocabulary terms and merges the most frequent pair into a new vocabulary word. When encountering new text for tokenization, the same merging process is applied by executing all recorded merges in the order they were performed during training. BPE's vocabulary initially consists of the characters present in the training data.


