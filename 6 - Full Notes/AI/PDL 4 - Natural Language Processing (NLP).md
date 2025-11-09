2025-11-07 10:40

Status:


Tags:
[[cs]] 
[[ai]] 
[[ml]] 
[[dl]] 
[[rl]] 


_______
# PDL 4 - Natural Language Processing (NLP)

*Note* → Video uses Hugging Face Transformers, Book uses Recurrent Neural Networks
- **Transformers:** architecture of neural networks → good at taking advantage of TPUs
### Preface knowledge:
**ULMFit:** model trained on a very large broad data set (wikipedia)
- Showed how pre-trained models can be very useful for training models for specific purposes
- I.e. train on wikipedia to predict next word → train on IMDB to predict next word → train to classify (good/bad)
	- Interesting because no need to label first 2
	- Transformer → replace predicting next word with guessing which words were deleted

**Document:** input to NLP model to be classified

**Natural Language Processing:** type of machine learning to help computers process / interact with natural language
- **Self-supervised learning:** don’t need to assign labelling data → learns data labels by itself
	- *Note* → normally used to pretrain a model for transfer learning

**Alternative approach to [[PDL - Terminology|transformers]]** → [[PDL 4 - Recurrent Neural Networks (NLP)]] 
___
**How to implement [[PDL 3 - Neural Net Foundations|neural network]] for words:** 
- **Tokenization:** split documents into tokens (words)
	- **Main approaches:** 
		- *Word* based → split by spaces, punctuation and language specific rules (i.e. `don't -> do n't`)
		- *Subword* based → split based on most common substrings 
			- Solves the problem that some languages don’t have space separated words + size of **vocabulary** (list of unique words)
			- I.e. start of a new word could be represented by `_X` + there can be the same parts multiple times
				- Larger vocab = larger substrings (can have more variety)
		- *Character* based → split into each individual character
	- **Special tokens:** 
		- `xxbos` → beginning of text
			- Makes it easier for model to recognize important parts of the sentence
		- `xxmaj` → indicates capital
		- `xxunk` → unknown word
- **Numericalization:** convert each token into a word based on where it is in the vocabulary
	- Treat each token like a category (get levels → distinct possible values)
	- *Note* → can replace low frequency tokens with `xxunk` to avoid using too much memory
- *Note* → have to make same decisions as the ones made in the model you used (to get same vocab)
	- Hugging face model hub:
		- Different architectures (which can be trained on different *corpuses* for models)
		- `deberta-v3` good
	- `AutoTokenizer.from_pretrained` → allows you to follow same decisions
- *Note* → for the input string, it needs to have some way of determining the information is given
	- I.e. separate the categories, words, etc. `TEXT1: ABC TEXT2: DEF` 
	- Each epoch: separate into streams
		- First shuffle order of documents (not text — need to preserve meaning)
		- Then, based on batch size, feed in mini-streams of tokens (broken up by `xxbos`)
			- Even if it’s broken into different length chunks or at different places → activation (and final output) stays consistent because hidden state preserves continuity
		- Each batch has part of each mini stream → so that it gets a bit of context of each mini stream at any one time
		- ![[Pasted image 20251108201913.png]]

**Pearson correlation coefficient ($r$):** metric that tells you how similar 2 variables are
- Between -1 and 1 → completely incorrect to completely correct
- ![[Pasted image 20251108124856.png|500]] 
- *Note* → when you have big outliers, this may skew the data a lot
	- Because it relies on the square of the data point distances
	- But you can’t just remove it without first investigating them + understanding where they came from (might exist in test data) → split into 2 separate analyses (shouldn’t be treated the same)
- **Best practice:** graph the data points of various levels of that metric
	- See what the data looks like at 0.9, 0.7, 0.2, etc.
- Transformer expects metrics to be returned as a dict (to know what label to use)

**Encoder:** The model not including the task-specific final layer(s).
- Allows you to train a predictor and remove the final layer to turn it into a classifier

___
**Implementing a classifier:** 
- *Note* → `DataLoader` requires a fixed shape for tensors (same length on every axis)
	- Can make shorter texts the same length as the biggest text (special padding token)
	- AND batch similar size texts together to save memory
- *Note* → when training the classifier, you can gradually unfreeze and use discriminative learning rates
	- Smaller learning rates for earlier layers, bigger learning rates for later
	- Unfreeze all at once for [[PDL - Terminology|computer vision]] 

# References

