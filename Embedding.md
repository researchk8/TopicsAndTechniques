# Embedding
One of the core enabling technologies for LLMs is vector embeddings. While computers cannot directly understand text, embeddings represent text numerically. All user-provided text is converted to embeddings, which are used to generate responses.

Embeddings databases are the engine that delivers semantic search. Data is transformed into embeddings vectors where similar concepts will produce similar vectors. Indexes both large and small are built with these vectors. The indexes are used to find results that have the same meaning, not necessarily the same keywords.

## Components

### Vectorize
The most compute intensive step in building an index is vectorization. The path parameter sets the path to the vector model. There is logic to automatically detect the vector model method but it can also be set directly.

The batch and encodebatch parameters control the vectorization process. Larger values for batch will pass larger batches to the vectorization method. Larger values for encodebatch will pass larger batches for each vector encode call. In the case of GPU vector models, larger values will consume more GPU memory.

Data is buffered to temporary storage during indexing as embeddings vectors can be quite large (for example 768 dimensions of float32 is 768 * 4 = 3072 bytes per vector). Once vectorization is complete, a mmapped array is created with all vectors for Approximate Nearest Neighbor (ANN) indexing.

### Index

#### Approximate Nearest Neighbor (ANN) index configuration for storing vector embeddings.

### Search


## Tools
- IngestAI / embedditor https://github.com/IngestAI/embedditor

## Embedding models
Making it possible to build retrieval augmented generation (RAG) applications that combine text prompts with existing documents or other data.

See 
- https://ollama.com/blog/embedding-models  
- https://lancedb.github.io/lancedb/embeddings/default_embedding_functions/

## Models

### nomic-embed-text (Ollama)

### sentence-transformers (Ollama)

### mistral-text-embeddings (Ollama)

### text-embedding-3-large (OpenAI)

### text-ada-002 (OpenAI)

## Embedders


    OpenAI
    Gemini
    Ollama
    Voyage AI
    Azure OpenAI
    Mistral
    Fireworks
    Together
    HuggingFace
    Qdrant FastEmbed


## Embedding Databases
Embeddings databases are the engine that delivers semantic search. Data is transformed into embeddings vectors where similar concepts will produce similar vectors. Indexes both large and small are built with these vectors. The indexes are used to find results that have the same meaning, not necessarily the same keywords.

### txtai
txtai is an all-in-one embeddings database for semantic search, LLM orchestration and language model workflows.
https://neuml.github.io/txtai/


# Resources
- https://neuml.github.io/txtai/embeddings/
- https://neuml.github.io/txtai/embeddings/indexing/
