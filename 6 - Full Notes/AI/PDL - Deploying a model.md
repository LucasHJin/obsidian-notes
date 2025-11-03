2025-11-01 17:40

Status:


Tags:
[[cs]] 
[[ai]] 
[[ml]] 
[[dl]] 
[[rl]] 



_______
# PDL - Deploying a model

**HuggingFace Spaces:** a hosting platform by Hugging Face where you can deploy and share interactive ML apps built with:
- Gradio, Streamlit, Static apps
- **Space:** like a repository where you can push your code and it auto builds and runs the Gradio app 

**Gradio:** a Python library that makes it easy to build interactive web UIs + deploy online/locally

*Note:* Hugging Face is the parent of HuggingFace Spaces (like github for AI models)
- Builds tools, models, platforms for machine learning
- Has:
	- Model hub
	- Dataset hub
	- Transformers library (pretrained models)
	- Inference API (run deployed models)

___
#### Deployment

**2 parts:** 
- Architecture + parameters

**Creating Gradio Interface:** 
- Wants a dictionary of all possible categories + probability of each one
	- I.e. `dict(zip(categories, map(float, probs)))` 
- Create a gradio interface
	- What function to get output, what are the inputs, what are the outputs, provide some exampls

*Note* → need a python script containing the information needed (i.e. no unnecessary things)
- Can do this in a Jupyter notebook
- Use `from nbdev.export import notebook2script` → can export only things marked by `#|export` 
	- So that you could use the jupyter notebook for testing and just export at the end

# References
[Saving a model (to be published)](https://www.kaggle.com/code/jhoward/saving-a-basic-fastai-model) 
