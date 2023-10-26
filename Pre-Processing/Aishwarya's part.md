````markdown
```python
# Preprocessing and Cleaning the data

from gensim.parsing.preprocessing import preprocess_string

from gensim.parsing.preprocessing import strip_multiple_whitespaces

from gensim.parsing.preprocessing import strip_short

from gensim.parsing.preprocessing import strip_punctuation

from gensim.parsing.preprocessing import strip_tags

from gensim.parsing.preprocessing import strip_numeric

from gensim.parsing.preprocessing import strip_non_alphanum

from gensim.parsing.preprocessing import strip_short

CUSTOM_FILTERS = [lambda x: x.lower(), strip_tags, strip_punctuation, strip_multiple_whitespaces, strip_numeric, strip_non_alphanum,  lambda x: strip_short(x, minsize=4)]

filtered_text = []

for item in df['content'].astype(str):

  filtered_text.append(preprocess_string(item, CUSTOM_FILTERS))

# Lemmatization

import nltk

nltk.download('wordnet')

from nltk.stem import WordNetLemmatizer

lemmatizer = WordNetLemmatizer()

lemmatized_words = [[lemmatizer.lemmatize(word) for word in sublst] for sublst in filtered_text]

print(lemmatized_words[0])

# Removing stop words

from gensim.parsing.preprocessing import remove_stopwords

from gensim.parsing.preprocessing import STOPWORDS

from nltk.tokenize import word_tokenize

nltk.download('punkt')

stop_words = STOPWORDS.union(set(['jats', 'ai', 'artificial', 'intelligence', 'research','technology','article',

                                  'development', 'paper', 'application', 'method','deep','algorithm', 'problem', 'model', 'iso', 'function',

                                  'noise', 'sample', 'layer', 'optimization', 'solution',

                                  'optimal', 'parameter', 'predict', 'forecast', 'cluster', 'classifier', 'label', 'class',

                                  'test', 'training', 'case', 'level', 'give', 'focus',

                                  'real', 'however', 'review', 'need', 'various', 'many', 'solve', 'analyze', 'human',

                                  'include', 'datasets','dataset','image', 'approach', 'accuracy', 'information',

                                  'also', 'time', 'show',  'provide', 'task', 'make',

                                  'performance', 'knowledge', 'user', 'feature', 'proposed','propose',

                                  'process', 'system', 'well', 'study',

                                  'different', 'high', 'improve', 'design', 'recognition',

                                  'train', 'compare', 'field', 'apply', 'develop', 'based',

                                  'technique', 'analysis', 'present', 'work',

                                  'learn', 'machine', 'language', 'large',

                                  'intelligent', 'base', 'neural', 'network', 'framework','learning',

                                  'result', 'use', 'supervised', 'representation', 'domain', 'architecture',

                                  'prediction', 'classification', 'natural', 'conference', 'data',

                                  'conclusion', 'objective', 'abstract','background', 'author', 'disclosure', 'title', 'computer', 'agent',

                                  'challenge','processing', 'future', 'recent', 'transfer', 'state', 'yang']))

s = ""

print(stop_words)

cleaned_text_list = []

for line in lemmatized_words:

  s = " ".join(line)

  tokenized_text = word_tokenize(s)

  cleaned_text = [word for word in tokenized_text if not word in stop_words]

  cleaned_text_list.append(cleaned_text)
````