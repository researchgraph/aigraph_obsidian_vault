
https://mark-riedl.medium.com/a-very-gentle-introduction-to-large-language-models-without-the-hype-5f67941fa59e

##### Encoders : 
A lot of words mean the same thing. The mechanism to convert the words into a specific format/ representation is what an encoder does
##### Decoders :
Takes up the encoding and picks the word with the highest electrical output to be returned as the "original word"

By forcing a large number of similar words to all fit into a small set of numbers, we force the network to make compromises and group words together that might trigger the same output word guess. This is a lot like file compression. This is how encoder-decoder network works.

##### Self supervised
No separate data for testing the output, the inputs and outputs are just compared.

##### Masked Language Models : 
Takes in a sequence of words and generates a sequence of words. One of the words in the sequence is masked out and the network makes guesses about what that word should be.

#### Generative model :
Has the mask at the end, meaning, the network is always guessing for the next word. This model is also called _autoregressive model_ since it is self-predictive. The network predicts a word, and uses that word to predict the next word and so on.

##### GPT - Generative Pretrained Transformer
- Generative - The model provides continuations to the provided input by guessing which word comes next.
- Pretrained - Model is already trained on a very large corpus of text that covers a wide range of topics taken from the internet instead of specialized repositories.
- Transformer - A self supervised encoder decoder deep learning model.

##### Self attention
A transformer learns which words in an input sequence are related and then creates a new encoding for each position in the input sequence that is a merger of all the related words. Happens in 3 stages:

(**1)** Each word in the input sequence is encoded as normal and four copies of the word encodings are made. One is called the _residual_ and set aside for safe keeping.

**(2)** A second round of encoding is then run on the other three. Each undergoes a different encoding process so they all become different. One is called a query (_q_), one a key (_k_), and one a value (_v_).

Self-attention works a bit like a _fuzzy_ hash table. When  a query is provided instead of looking for an exact match with a key, it finds approximate matches based on the similarity between query and key. If the match isn’t a perfect match,  it returns some fraction of the value.

For each word position in the input,  the _q_ encoding and the _k_ encoding are taken and the cosine similarity is calculated. The similarity is recorded in a matrix called the _self-attention scores_. The self-attention scores are then multiplied with the v encodings to get the best matched words.

(**3**) The results are then added to the residual. The result will likely be a mix of words and the final _transformed_ encoding  will be sent to the decoder. A fake word in each position that really encodes two or more words is more useful for making predictions based on a single word per position.

##### Concerns around Large Language models

1. [[Large Language Models]] are trained on the internet, meaning they are privy to all the dark parts of humanity including racism, insults of every kind against every type of person, political misinformation etc
2. LLMs don't have a fixed stance on things. One can ask a large language model to write a sentence in favor of something, or against that same thing, and the language model will comply both ways.
3. They do not have a sense of truth or right or wrong. It could give responses like the Earth is flat, although it is false simply because enough people on the internet would have been flat earthers and their opinions were also learnt by the LLM.
4. LLMs can make mistakes. The training data might have a lot of inconsistent material or has seen a word more times that it prefers that word even when it doesn't make sense for the input, leading to a phenomenon called “**hallucination**” .
5. LLMs are auto-regressive. Thus, when they make poor guesses, those guessed words get added to their own inputs to make the next word guess. So errors build up.
6. Outputs of LLMs should always be verified.
7. The quality of response is directly proportional to the quality of the input prompt.
8. LLMs cant remember conversations. As a conversation is happening, it gets logged making the conversation seem coherent for a while. Eventually, the accumulated log will get too large and the beginning of the conversation will be deleted and the system will “forget” earlier things.
9. Large language models don't do problem solving or planning as they can't “think through the alternatives” or tried one thing and backtracked and tried another thing. There is no mechanism inside a transformer that one could point to that would do such a back-and-forth consideration of the future.


Measures that have made LLMs better:

**Instruction tuning** - When a wrong response is received, what the right response should be is written down and  the original input and the new, corrected output  are sent through the neural network as training data. With enough examples of the corrected output, the system will learn to shift it’s circuit so that the new answer is preferred.

**Reinforcement Learning with Human Feedback** - Reward based system. Reinforcement learning systems attempt to predict how much future reward they will get and then choose the action that is most likely going to get more future reward.


