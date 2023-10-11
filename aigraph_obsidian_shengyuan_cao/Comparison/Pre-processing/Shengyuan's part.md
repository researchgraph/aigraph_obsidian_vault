````markdown
```python
def clean_text_round1(abstract):  
    """Remove HTML labels,  
    and remove redundant words and line breaks"""    abstract = re.sub('<[^>]+>', '', str(abstract))  
    abstract = re.sub('Abstract', '', str(abstract))  
    abstract = re.sub('\n', '', str(abstract))  
    return abstract.strip()  
  
  
# Clean Speech Text  
df["abstract"] = df["abstract"].apply(lambda x: clean_text_round1(x))  
  
  
# Noun extract and lemmatize function  
def nouns(abstract):  
    """Given a string of text, tokenize the text  
    and pull out only the nouns."""    # create mask to isolate words that are nouns  
    is_noun = lambda pos: pos[:2] == 'NN'  
    # store function to split string of words  
    # into a list of words (tokens)    tokenized = word_tokenize(abstract)  
    # store function to lemmatize each word  
    wordnet_lemmatizer = WordNetLemmatizer()  
    # use list comprehension to lemmatize all words  
    # and create a list of all nouns    all_nouns = [wordnet_lemmatizer.lemmatize(word) for (word, pos) in pos_tag(tokenized) if is_noun(pos)]  
  
    # return string of joined list of nouns  
    return ' '.join(all_nouns)  
  
  
# Create dataframe of only nouns from speeches  
data_nouns = pd.DataFrame(df.abstract.apply(nouns))  
  
stop_noun = [  
    "evolutionary", "program", "strategy", "vector", "number", "chapter", "theory", 'image',  
    'fuzzy', 'computer', "agent", "function", "noise", "sample", "layer", "optimization",  
    "solution", "optimal", 'parameter', 'predict', 'forecast', 'cluster', 'datasets', 'classifier',  
    'label', 'class', 'test', 'training', 'case', 'level', 'give', 'focus', 'real', 'however',  
    'review', 'need', 'various', 'many', 'solve', 'analyze', 'human', 'include',  
    'dataset', 'feature', 'performance', 'approach', 'accuracy', 'development', 'information',  
    'also', 'time', 'show', 'provide', 'task', 'make', 'performance', 'approach',  
    'information', 'knowledge', 'user', 'feature', "propose", "process", 'improve',  
    'design', 'recognition', 'train', 'compare', 'field', 'apply', 'develop', 'improve', 'review'  
                                                                                         "include", "technology",  
    "technique", "research", "analysis", "present", "work",  
    'learning', 'paper', 'machine', 'learn', 'artificial', 'intelligence', 'language',  
    'intelligent', 'deep', 'base', 'neural', 'network', 'model', "framework", "information"  
                                                                              'approach', 'result', 'use', 'method',  
    'algorithm', 'application',  
    'prediction', 'classification', 'natural', 'conference', 'article', 'data',  
    'conclusion', 'objective', 'abstract', 'background', 'author', 'disclosure', 'title',  
    "a", "an", "the", "in", "on", "at", "from", "to", "with", "over", "under",  
    "and", "but", "or", "so", "nor", "for", "yet", "i", "you", "he", "she",  
    "it", "we", "they", "me", "him", "her", "us", "them", 'purpose', 'base'  
                                                                     "is", "am", "are", "was", "were", "be", "been",  
    "being",  
    "have", "has", "had", "do", "does", "did", "will", "shall",  
    "can", "could", "would", "should", "may", "might", "must", "ought", "that",  
    "this", "these", "those", "how", "what", "why", "by", "their", "of", "as", "there",  
    "within", "which",  
    # Add more stop words here if needed  
]
# Store TF-IDF Vectorizer  
tv_noun = TfidfVectorizer(stop_words=stopwords.words('english') + stop_noun, ngram_range=(1, 2), max_df=.8, min_df=.01)  
# Fit and Transform speech noun text to a TF-IDF Doc-Term Matrix  
data_tv_noun = tv_noun.fit_transform(data_nouns.abstract)  
# Create data-frame of Doc-Term Matrix with nouns as column names  
data_dtm_noun = pd.DataFrame(data_tv_noun.toarray(), columns=tv_noun.get_feature_names_out())  
# Set President's Names as Index  
data_dtm_noun.index = df.index  
# Visually inspect Document Term Matrix  
data_dtm_noun.head()  
  
  
def display_topics(model, feature_names, num_top_words, topic_names=None):  
    for ix, topic in enumerate(model.components_):  
        topic_words = [(feature_names[i], topic[i]) for i in topic.argsort()[:-num_top_words * 3 - 1:-1]]  
  
        # Check for duplicates and sub-strings in bigrams  
        to_remove = set()  
        for i, (word_i, _) in enumerate(topic_words):  
            components_i = word_i.split()  
  
            # remove exact duplicates like "system system"  
            if len(components_i) == 2 and components_i[0] == components_i[1]:  
                to_remove.add(word_i)  
                continue  
  
            for j, (word_j, _) in enumerate(topic_words):  
                if i != j:  
                    if len(components_i) == 1 and word_i in word_j:  
                        # if word_i is a substring of word_j and word_i is not a bigram, then word_i should be removed  
                        to_remove.add(word_i)  
  
        # Save only words that have not been marked for removal
        topic_words = [(word, importance) for word, importance in topic_words if word not in to_remove]  
  
        # Finally, to ensure the number of words output, we filter again
        top_words = sorted(topic_words, key=lambda x: x[1], reverse=True)[:num_top_words]  
        words = [word for word, _ in top_words]  
  
        if not topic_names or not topic_names[ix]:  
            print("\nTopic ", ix)  
        else:  
            print("\nTopic: '", topic_names[ix], "'")  
        print(", ".join(words))
````