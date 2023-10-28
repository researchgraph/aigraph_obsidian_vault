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

nltk.download('punkt')

  

stop_words = STOPWORDS.union(set(['jats', 'ai', 'artificial', 'intelligence', 'research','technology','article', 'pattern','compared',

                                  'development', 'paper', 'application', 'method','deep','algorithm', 'problem', 'model', 'iso', 'function',

                                  'noise', 'sample', 'layer', 'optimization', 'solution','term','including', 'factor','tool','main','experimental',

                                  'optimal', 'parameter', 'predict', 'forecast', 'cluster','classifier', 'label', 'class','input','world',

                                  'test', 'training', 'case', 'level', 'give', 'focus','change','current','point','important','number','strategy',

                                  'real', 'however', 'review', 'need', 'various', 'many', 'solve', 'analyze', 'human','significant','source',

                                  'include', 'datasets','dataset','image', 'approach', 'accuracy', 'information','component','potential',

                                  'also', 'time', 'show',  'provide', 'task', 'make','existing','multiple','making','activity','search',

                                  'performance', 'knowledge', 'user', 'feature', 'proposed','propose','year','related','efficient','rate',

                                  'process', 'system', 'well', 'study','form','effective','example','better','characteristic','support',

                                  'different', 'high', 'improve', 'design', 'recognition','specific','finally','novel','order','purpose',

                                  'train', 'compare', 'field', 'apply', 'develop', 'based','content','impact','possible','error','presented',

                                  'technique', 'analysis', 'present', 'work','condition','implementation','evaluation','increase','target',

                                  'learn', 'machine', 'language', 'large','issue','value','given','higher','context','scale','complex',

                                  'intelligent', 'base', 'neural', 'network', 'framework','learning','developed','best','multi','fuzzy',

                                  'result', 'use', 'supervised', 'representation', 'domain', 'architecture','provides','obtained','like',

                                  'prediction', 'classification', 'natural', 'conference', 'data','identify','concept','available','world',

                                  'conclusion', 'objective', 'abstract','background', 'author', 'disclosure', 'title', 'computer', 'agent',

                                  'challenge','processing', 'future', 'recent', 'transfer', 'state', 'yang','evolutionary','program','combination',

                                  'vector','chapter','theory','aim','addition', 'step','cost','type','part','efficiency','complexity',

                                  'comparison','set','experiment','measure','quality','operation','difference','direction','practice',

                                  'platform','range','researcher','area','stage','object','structure','decision','mean','finding','response',

                                  'effect','group','effectiveness','size','people','way','science','question','role','requirement','goal',

                                  'implement','nan', 'mechanism', 'modeling','second','considered','space','simulation','internet',

                                  'standard','variable','physical','interaction','local','methodology','spatial','smart','significantly',

                                  'a', 'an', 'the', 'in', 'on', 'at', 'from', 'to', 'with', 'over', 'under','and', 'but', 'or', 'so', 'nor', 'for',

                                  'yet', 'i', 'you', 'he', 'she','it', 'we', 'they', 'me', 'him', 'her', 'us', 'them','is', 'am', 'are', 'was',

                                  'were', 'be', 'been', 'being','have', 'has', 'had', 'do', 'does', 'did', 'will', 'shall','can', 'could', 'would',

                                  'should', 'may', 'might', 'must', 'ought', 'that','this', 'these', 'those', 'how', 'what', 'why', 'by', 'their',

                                  'of', 'as', 'there','within', 'which']))

  
  

s = ""

print(stop_words)

cleaned_text_list = []

for line in lemmatized_words:

  s = " ".join(line)

  tokenized_text = word_tokenize(s)

  cleaned_text = [word for word in tokenized_text if word.lower() not in stop_words]

  cleaned_text_list.append(cleaned_text)