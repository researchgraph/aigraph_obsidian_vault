````markdown
```python
nltk.download('punkt')

nltk.download('wordnet')

nltk.download('stopwords')

nltk.download('averaged_perceptron_tagger')

stop_words = list(set(nltk.corpus.stopwords.words('english')))

# remove stop words

  

stop_words_ = [

"evolutionary", "program", "strategy", "vector", "number", "chapter", "theory", 'image',

'fuzzy', 'computer', "agent", "function", "noise", "sample", "layer", "optimization",

"solution", "optimal", 'parameter', 'predict', 'forecast', 'cluster', 'datasets', 'classifier',

'label', 'class', 'test', 'training', 'case', 'level', 'give', 'focus','real', 'however',

'review', 'need', 'various', 'many', 'solve', 'analyze', 'human','include',

'dataset', 'feature', 'performance', 'approach', 'accuracy', 'development', 'information',

'also', 'time', 'show',  'provide', 'task', 'make', 'performance', 'approach',

'information', 'knowledge', 'user', 'feature', "propose", "process", 'improve',

'design', 'recognition',  'train', 'compare',  'field', 'apply', 'develop', 'improve', 'review'

"include", "technology", "technique", "research", "analysis", "present", "work",

'learning', 'paper', 'machine', 'learn', 'artificial','intelligence', 'language',

'intelligent', 'deep', 'base', 'neural', 'network', 'model', "framework", "information"

'approach', 'result', 'use', 'method', 'algorithm', 'application',

'prediction', 'classification', 'natural', 'conference', 'article', 'data',

'conclusion', 'objective', 'abstract','background', 'author', 'disclosure', 'title',

"a", "an", "the", "in", "on", "at", "from", "to", "with", "over", "under",

"and", "but", "or", "so", "nor", "for", "yet", "i", "you", "he", "she",

"it", "we", "they", "me", "him", "her", "us", "them",'purpose', 'base'

"is", "am", "are", "was", "were", "be", "been", "being",

"have", "has", "had", "do", "does", "did", "will", "shall",

"can", "could", "would", "should", "may", "might", "must", "ought", "that",

"this", "these", "those", "how", "what", "why", "by", "their", "of", "as", "there",

"within", "which",

# Add more stop words here if needed

]

stop_words.extend(stop_words_)

def remove_something(sentence):

    text = sentence.replace("<jats:title content-type=\"abstract-subheading\">", ' ')

    text = text.replace("&amp;lt;p&amp;gt;", " ")

    text = text.replace("<jats:sec id=\"sec001\">", " ")

    text = text.replace("<jats:sec>", ' ')

    text = text.replace("</jats:sec>",' ')

    text = text.replace("<jats:title>", " ")

    text = text.replace("</jats:title>", " ")

    text = text.replace("&#x0D", " ")

    text = text.replace("-", " ")

    text = text.replace("<jats:p>", ' ')

    text = text.replace("</jats:p>", ' ')

    text = text.replace("<title>", ' ')

    text = text.replace("</title>", ' ')

    text = text.replace("<sec>", ' ')

    text = text.replace("</sec>", ' ')

    # reomove digits

    text = re.sub(r'\d+', '', text)

    return text

  

def get_wordnet_pos(treebank_tag):

    if treebank_tag.startswith('J'):

        return wordnet.ADJ

    elif treebank_tag.startswith('V'):

        return wordnet.VERB

    elif treebank_tag.startswith('N'):

        return wordnet.NOUN

    elif treebank_tag.startswith('R'):

        return wordnet.ADV

    else:

        return wordnet.NOUN

  

from nltk import pos_tag

# Initialize the WordNet lemmatizer

lemmatizer = WordNetLemmatizer()

def clean_text(text):

    text = remove_something(text)

    lemmatized_set = set()

    lemmatized_words = []

    terms_dict = defaultdict(int)

    text = text.lower()

    # remove punctuation

    translator = str.maketrans('', '', string.punctuation)

    text = text.translate(translator)

    # Tokenize the input text into words

    words = nltk.word_tokenize(text)

    tagged_words = nltk.pos_tag(words)

    # Lemmatize each word in the text

    for word, tag in tagged_words:

      if word.isdigit(): continue

      if len(word) <= 3: continue

      pos = get_wordnet_pos(tag)

      word = lemmatizer.lemmatize(word, pos)

      if word in stop_words: continue

      lemmatized_words.append(word)

      terms_dict[word] += 1

  

    # Join the lemmatized words back into a single text

    lemmatized_set = set(lemmatized_words)

    # cleaned_text = ' '.join(lemmatized_words)

  

    return lemmatized_words, lemmatized_set, terms_dict

  

def translate_to_english(text):

  translator = Translator()

  translated_text = translator.translate(text, src='auto', dest='en')

  return translated_text.text

with open('/content/grive/MyDrive/Colab Notebooks/data/10000_ai_ml_dp_nlp.json', 'r') as file:

    data = json.load(file)

  

    # preprocessing

    training_texts = []

    training_texts_title = []

    lemmatized_words_all = []

    article_ls = []

    training_texts_title_abstract = []

    words = set()

    terms_dict_all = defaultdict(int)

    # print(data[0])

    k=0

  

    # for item in data:

    for article in data:

      if "abstract" in article.keys() and "title" in article.keys():

        text_title_abstract = article['abstract'] + " " + article['title'][0];

        # text_title_abstract_ori = text_title_abstract

        language = detect(text_title_abstract)

        if language != "en":

          print("Before translate: "+ text_title_abstract)

          if len(text_title_abstract) >=5000:

            text_title_abstract = text_title_abstract[:5000]

  

          text_title_abstract = translate_to_english(text_title_abstract)

          print("After translate: "+ text_title_abstract)

          print("------")

        lemmatized_words,lemmatized_set, terms_dict = clean_text(text_title_abstract)

        words.update(lemmatized_set)

        terms_dict_all.update(terms_dict)

        lemmatized_words_all.append(lemmatized_words)

        data_article = Article(index=k, _id=article["_id"], abstract='',

                        abstract_ori=article['abstract'], title='',

                        title_ori=article['title'][0], title_abstract='', tokens=[])

        article_ls.append(data_article)

  
  

      k += 1

    print(len(article_ls))

    avoiding_words = set(sorted(terms_dict, key=lambda x: terms_dict[x], reverse=True)[:50]) # high frequent words

    low_frequency_terms = set([term for term in terms_dict if terms_dict[term] == 1]) # low frequent words

    avoiding_words |= low_frequency_terms

    print(f"avoiding_words: {avoiding_words}")

    training_texts_title_abstract = [' '.join(term for term in terms_list if term not in avoiding_words) for terms_list in lemmatized_words_all]

    training_texts_title_abstract[:5]

    for i, article in enumerate(article_ls):

      tokens = nltk.word_tokenize(training_texts_title_abstract[i])

      article.tokens = tokens

      article.title_abstract = training_texts_title_abstract[i]
