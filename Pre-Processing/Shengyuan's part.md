````markdown
```python
def clean_text_round1(abstract):  
    """Remove HTML tags, redundant words, and line breaks"""  
    abstract = re.sub('<[^>]+>', '', str(abstract))  
    abstract = re.sub('Abstract', '', str(abstract))  
    abstract = re.sub('\n', '', str(abstract))  
    return abstract.strip()  
  
  
# Clean the abstract text  
df["abstract"] = df["abstract"].apply(lambda x: clean_text_round1(x))  
  
  
def nouns(abstract):  
    """Tokenize text, extract only the nouns, and lemmatize them"""  
    is_noun = lambda pos: pos[:2] == 'NN'  
    tokenized = word_tokenize(abstract)  
    wordnet_lemmatizer = WordNetLemmatizer()  
    all_nouns = [wordnet_lemmatizer.lemmatize(word) for (word, pos) in pos_tag(tokenized) if is_noun(pos)]  
    return ' '.join(all_nouns)  
  
  
# Create a DataFrame of only nouns from the abstracts  
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
    'design', 'recognition', 'train', 'compare', 'field', 'apply', 'develop', 'improve', 'review',  
    "include", "technology", "technique", "research", "analysis", "present", "work",  
    'learning', 'paper', 'machine', 'learn', 'artificial', 'intelligence', 'language',  
    'intelligent', 'deep', 'base', 'neural', 'network', 'model', "framework", "information",  
    'approach', 'result', 'use', 'method', 'algorithm', 'application',  
    'prediction', 'classification', 'natural', 'conference', 'article', 'data',  
    'conclusion', 'objective', 'abstract', 'background', 'author', 'disclosure', 'title',  
    "a", "an", "the", "in", "on", "at", "from", "to", "with", "over", "under",  
    "and", "but", "or", "so", "nor", "for", "yet", "i", "you", "he", "she",  
    "it", "we", "they", "me", "him", "her", "us", "them", 'purpose', 'base',  
    "is", "am", "are", "was", "were", "be", "been", "being",  
    "have", "has", "had", "do", "does", "did", "will", "shall",  
    "can", "could", "would", "should", "may", "might", "must", "ought", "that",  
    "this", "these", "those", "how", "what", "why", "by", "their", "of", "as", "there",  
    "within", "which", "nan", "issue", "implement", "implementation", "goal", "evaluation", "component", "requirement",  
    "support", "role", "question", "challenge", "science", "concept", "way", "people", "problem", "example",  
    "result", "results", "architecture", "size", "effectiveness", "group", "state", "effect", "response", "finding",  
    "input", "mean", "value", "decision", "structure", "representation", "characteristic", "object", "stage",  
    "activity", "year", "area", "researcher", "range", "tool", "platform", "practice", "domain", "term", "condition",  
    "direction", "difference", "operation", "quality", "measure", "source", "processing", "pattern", "experiment",  
    "set", "comparison", "combination", "rate", "complexity", "efficiency", "part", "factor", "type", "form", "point",  
    "cost", "step", "error", "addition", "aim",  
    'jats', 'ai', 'artificial', 'intelligence', 'research', 'technology', 'article', 'pattern', 'compared',  
    'development', 'paper', 'application', 'method', 'deep', 'algorithm', 'problem', 'model', 'iso', 'function',  
    'noise', 'sample', 'layer', 'optimization', 'solution', 'term', 'including', 'factor', 'tool', 'main',  
    'experimental',  
    'optimal', 'parameter', 'predict', 'forecast', 'cluster', 'classifier', 'label', 'class', 'input', 'world',  
    'test', 'training', 'case', 'level', 'give', 'focus', 'change', 'current', 'point', 'important', 'number',  
    'real', 'however', 'review', 'need', 'various', 'many', 'solve', 'analyze', 'human', 'significant', 'source',  
    'include', 'datasets', 'dataset', 'image', 'approach', 'accuracy', 'information', 'component', 'potential',  
    'also', 'time', 'show', 'provide', 'task', 'make', 'existing', 'multiple', 'making', 'activity', 'search',  
    'performance', 'knowledge', 'user', 'feature', 'proposed', 'propose', 'year', 'related', 'efficient',  
    'process', 'system', 'well', 'study', 'form', 'effective', 'example', 'better', 'characteristic', 'support',  
    'different', 'high', 'improve', 'design', 'recognition', 'specific', 'finally', 'novel', 'order', 'purpose',  
    'train', 'compare', 'field', 'apply', 'develop', 'based', 'content', 'impact', 'possible', 'error', 'presented',  
    'technique', 'analysis', 'present', 'work', 'condition', 'implementation', 'evaluation', 'increase', 'target',  
    'learn', 'machine', 'language', 'large', 'issue', 'value', 'given', 'higher', 'context', 'scale', 'complex',  
    'intelligent', 'base', 'neural', 'network', 'framework', 'learning', 'developed', 'best', 'multi', 'fuzzy',  
    'result', 'use', 'supervised', 'representation', 'domain', 'architecture', 'provides', 'obtained', 'like',  
    'prediction', 'classification', 'natural', 'conference', 'data', 'identify', 'concept', 'available', 'world',  
    'conclusion', 'objective', 'abstract', 'background', 'author', 'disclosure', 'title', 'computer', 'agent',  
    'challenge', 'processing', 'future', 'recent', 'transfer', 'state', 'yang'  
    # Add more stop words here if needed  
]
```
```