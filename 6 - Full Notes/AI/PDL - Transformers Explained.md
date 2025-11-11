2025-11-09 23:38

Status:


Tags:
[[cs]] 
[[ai]] 
[[ml]] 
[[dl]] 
[[rl]] 


_______
# PDL - Transformers Explained

### *Attention Is All You Need* 

**Transformer:** a machine learning model (neural network) that processes sequences all at once using a mechanism called **self-attention** → can consider relationship between any 2 elements in a sequence regardless of distance
- **Components:** 
	- *Input embedding* → convert tokens into vectors
	- *Positional encoding* → keep track of order (because of simultaneous processing) (i.e. 1, 2, 3, 4…)
	- *Self attention* → assign attention scores to all other tokens 
	- *Feedforward layers* → after attention, pass each token through a small neural network to process information further
	- *Layer Normalization & Residual Connections* → normalizing activations of a layer across features for input + add the input of a layer directly to its output (easier gradient flow in backpropogation)
	- *Stacking layers* → have multiple layers of attention + feedforward blocks (more complex)
- **Attention:** determines what it needs to pay attention to in the input sentence to predict the output sentence
- **Self attention:** allows a nn to understand the context of the words around a word

**Usecases:** when you have data whose sequence is important 
- NLP
- Text
- Audio
- Vision (ViT)

___
### *An Image is Worth 16x16 Words* 

**Vision Transformer (ViT):** method of processing images instead of using [[PDL - Terminology|CNNs]] → treats an image like a sequence of patches (like how a transformer treats a sentence as a sequence of words)
- **Components:** 
	- Divide into 16x16 patches and flatten into vectors
		- **Patches:** small segments of the image
	- Project each patch vector to higher dimensions to get patch embeddings (pass through a linear layer)
	- Add positional encoders
	- Feed the sequence through a standard transformer architecture (self attention + feedforward layers)
	- **Classification token (CLS)** → added to sequence (final embedding used for image classification)
	- The CLS representation is passed through a classifier to predict label



# References

