[https://arxiv.org/abs/1707.02919](https://arxiv.org/abs/1707.02919)

#Metrics #Comparison #Text-Mining 
## Research Objectives
- **Aim 1**: To provide an overview of the fundamental algorithms and techniques used in text mining, particularly in the biomedical domain.
- **Aim 2**: To discuss the challenges associated with evaluating summarization methods and the importance of question answering in the biomedical domain.

## Clustering Methods
The paper discusses two clustering algorithms:
- k-means
- Hierarchical clustering

## Evaluation Metrics
- The paper evaluates text classification using traditional metrics like accuracy, precision, recall, and F-1 score.

## Experimental Results
1. **Challenges in Evaluation**: Evaluating the quality of summaries in the biomedical domain is difficult due to its subjectivity and the labor-intensive nature of manual evaluations.
2. **ROUGE Metrics**: An automated technique for summary evaluation, ROUGE measures the quality by comparing automatically generated summaries with human-created ideal summaries.

## Conclusions and Issues
- The paper provides a comprehensive overview of algorithms and techniques in text mining, emphasizing their applicability in the biomedical domain.
- It also discusses the challenges and nuances of evaluating summary methods and highlights the role of question answering in biomedical research.

### ROUGE Metrics Explained
- **ROUGE-N**: Measures the overlap of n-grams between system and reference summaries.
  - **ROUGE-1**: Overlap of unigrams.
  - **ROUGE-2**: Overlap of bigrams; potentially useful for projects using bigram-based codes.
- **ROUGE-L**: Utilizes Longest Common Subsequence (LCS) for evaluation.
- **ROUGE-W**: Weighted LCS-based metrics favoring consecutive LCSes.
- **ROUGE-S**: Skip-bigram based co-occurrence statistics.
- **ROUGE-SU**: Skip-bigram plus unigram-based co-occurrence statistics.
