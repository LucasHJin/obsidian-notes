2025-10-13 11:19

Status:


Tags:
[[cs]] 
[[ai]] 
[[ml]] 
[[llm]]


_______
# LLM - Retrieval Augmented Generation (RAG)

**RAG:** a technique that combines information retrieval with text generation 
- I.e. it retrieves more information to provide context when generating a response
- **Pipeline:** 
	- *Retriever* → Finds relevant information from a knowledge base
	- *Generator* → Uses that information (as context) to produce the final answer
- **Solve LLM challenges:** 
	- No source
	- Out of date info

**Implementation:** 
- *High level overview:* 
	- LLM has a prompt → tells it to retrieve data + combine it with the user content (question)
	- Then, generate the response given additional information
- *Low level overview:* 
	- ==Indexing==
		- Load data
		- Turn data into vector embeddings (preserve meaning)
			- Store in a DB as vectors
			- **Split context into chunks → can fix into context window of LLM**
	- ==Retrieval==:
		- Convert the initial question into vector embeddings
		- Compare this embedding against document embeddings (**semantic search**) 
	- ==Augmentation==: process where retrieved data is injected into the prompt at run time
		- Append the semantic search result to the prompt
	- ==Generation==:
		- Generates response given semantic relevant data (using own llm reasoning)

**Strategies:** 
- Chunking strategy → size and overlap of each chunk
- Embedding strategy → which embedding model to use
- Retrieval strategy → how similar do words need to be + additional filtres

# References
- https://www.youtube.com/watch?v=T-D1OfcDW1M
- 
