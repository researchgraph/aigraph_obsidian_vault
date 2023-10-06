[https://doi.org/10.48550/arXiv.1607.01759](https://doi.org/10.48550/arXiv.1607.01759)

Models based on neural networks achieve very good performance in practice, but they tend to be relatively slow both at train and test time, limiting their use on very large datasets.
So, linear classifiers are often used as strong baselines for [[Text Classification]] problems. They often obtain state-of-the-art performances if the right features are
used and can be scaled to very large corpus.

#### Creating a simple baseline
Represent sentences as bag of words and train a linear classifier, e.g., a logistic regression or an SVM.
#### Limitation with linear classifiers
They do not share parameters among features and classes. This possibly limits their generalization in the
context of large output space where some classes
have very few examples. 
**Solution** : Factorize the linear classifier into low rank matrices or use multilayer neural networks

#### Aim : 
To explore ways to scale these
baselines to very large corpus with a large output
space, in the context of text classification. 

#### Architecture : 
- The Weight matrix : A look up table over the words
- Word representations are averaged into a text representation
- Text representation is a hidden variable which is fed into the linear classifier, fastText
- The probability distribution over the predefined classes is calculated using Hierarchical softmax
- Bag of n-grams is used as an additional feature to capture some partial information about the local word order.

#### Results
- Bigram information improves the performance by 1-4%.
- Using n-grams up to 5 leads to the best performance
- fastText takes less than a minute to train on the datasets

#### Inference
Linear models with a rank constraint and a fast loss approximation can train on a billion words within ten minutes, while achieving performance on par with the state-of-the-art for tag prediction and sentiment
analysis.
