
https://upstream.force11.org/attempts-at-automating-journal-subject-classification/

 Subject classification is done to help combine resources by subject, enabling the user to discover publications based on different levels of subject specificity. It can also be used to help determine where to publish and the direction a particular author may be pursuing in their research. Currently, most subject classification is done manually as it requires a lot of training. But this means, a standardized approach to classifying items is prevented.

**Dataset** : All Science Journal Classification Codes  - a table of journal and article titles and their corresponding subjects
**Procedure** : Preprocessing and multi-label classification  (since zero or many subjects can be assigned to a journal)
**Evaluation criteria** : micro F1 score

**Method 1** - TF-IDF + Linear Support Vector Classification
F1 score - 0.73

**Method 2** - Embeddings(provides more semantic weight on the data rather than simple occurrence of the words in the document) + Linear Support Vector Classification
F1 score - 0.71

**Method 3** - OpenAI: LLM + sentence completion
ChatGPT was asked to figure out what topics an existing journal title belonged to, and it came very close to predicting the correct answer. The author also asked it to figure out to which topic multiple Dutch journal article titles belonged, and it predicted the correct answer again
F1 score - 0.69

All 3 methods yielded similar results.

