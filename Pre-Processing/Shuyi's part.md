````markdown
```python

import nltk

from nltk.tokenize import word_tokenize

from nltk.corpus import stopwords

from nltk.corpus import wordnet

from nltk.stem import WordNetLemmatizer

nltk.download('punkt')

nltk.download('stopwords')

nltk.download('wordnet')

nltk.download('averaged_perceptron_tagger')

def get_pos(tag):

  if tag.startswith('J'):

    return wordnet.ADJ

  elif tag.startswith('V'):

    return wordnet.VERB

  elif tag.startswith('N'):

    return wordnet.NOUN

  elif tag.startswith('R'):

    return wordnet.ADV

  else:

    return None

training_texts = df['abstract']

sentences_list = []

lemmatizer = WordNetLemmatizer()

avoiding_words = []

stop_words = set(stopwords.words('english'))

terms_dict = {}

for sentence in training_texts:

  cleaned_sentence = re.sub('<[^<]+?>','',sentence)

  cleaned_sentence = re.sub(r'[^a-zA-Z ]','', cleaned_sentence)

  words = word_tokenize(cleaned_sentence)

  tagged_words = nltk.pos_tag(words)

  lemmatized_words = []

  for word_tag_pair in tagged_words:

    lemmatized_word = lemmatizer.lemmatize(word_tag_pair[0],pos=get_pos(word_tag_pair[1]) or wordnet.NOUN).lower()

    if lemmatized_word not in stop_words and len(lemmatized_word)>2:

      lemmatized_words.append(lemmatized_word)

      if lemmatized_word in terms_dict:

        terms_dict[lemmatized_word] += 1

      else:

        terms_dict[lemmatized_word] = 1

  sentences_list.append(lemmatized_words)

avoiding_words = set(sorted(terms_dict, key=lambda x: terms_dict[x], reverse=True)[:50])

print(f"avoiding_words: {avoiding_words}")

low_frequency_terms = set([term for term in terms_dict if terms_dict[term] == 1])

avoiding_words |= low_frequency_terms

sentences_list = [' '.join(term for term in terms_list if term not in avoiding_words) for terms_list in sentences_list]

sentences_list[:5]
````