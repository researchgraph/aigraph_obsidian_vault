[https://www.datacamp.com/tutorial/stemming-lemmatization-python](https://www.datacamp.com/tutorial/stemming-lemmatization-python)

 Inflection is a process of word formation, in which a word is modified to express different grammatical categories such as tense, case, voice etc.

#### Stemming
- Stemming reduces an inflected word to its word stem.
- Useful for dealing with sparsity and/or standardizing vocabulary
- Reduces redundancy and allows NLP models to learn links between inflected words and their word stem, which helps the model understand their usage in similar contexts.
- Functions by taking a list of frequent prefixes and suffixes found in inflected words and chopping off the end or beginning of the word.
Disadvantages:
- Can reduce separate inflected words to the same word stem even though they are not related 
Eg: "universal", "university", and "universe" all get stemmed to the same word although they are from different domains
- Can reduce inflected words to different word stems, but they should be the same
Eg: “alumnus,” “alumnae,” and “alumni” should have the same word stem, but they do not using PorterStemmer
- Stemmers become more complicated to design for languages that have more verb inflections or noun declensions like Italian or Russian

#### Lemmatization
The algorithmic process of identifying an inflected word’s “lemma" (dictionary form) based on its intended meaning.

- Relies on accurately determining the intended part of speech and the meaning of a word based on its context
- Because meanings of words are derived from a dictionary, lemmatization is a time consuming process.


For speed and efficiency, use stemming
For accuracy, use lemmatization

