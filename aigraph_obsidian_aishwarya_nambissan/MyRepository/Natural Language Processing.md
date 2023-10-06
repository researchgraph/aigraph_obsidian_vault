https://medium.com/@ageitgey/natural-language-processing-is-fun-9a0bff37854e

Natural Language Processing is to enable computers to understand and process human languages. It is difficult since human languages aren't consistent or logical.

NLP Strategy: Build a pipeline of steps to follow to solve each part of a problem broken down into smaller problems

##### Building an NLP Pipeline
1.Sentence segmentation

2.Word tokenization

3.Predicting parts of speech for each token by feeding each word into a pre-trained part-of-speech classification model

4.Text lemmatization by having a look-up table of the lemma forms of words based on their part of speech and possibly having some custom rules to handle new words

5.Identifying stop words

6.Dependency parsing - to figure out how all the  words in our sentence relate to each other.

	a)Finding noun phrases
7. Named Entity Recognition (NER) - detect and label nouns with the real-world concepts that they represent.

8. Coreference Resolution - tracking pronouns across sentences
