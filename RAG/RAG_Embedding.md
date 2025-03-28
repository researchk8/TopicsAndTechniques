# Embedding

Embeddings databases are the engine that delivers semantic search. Data is transformed into embeddings vectors where
similar concepts will produce similar vectors. Indexes both large and small are built with these vectors. The indexes
are used to find results that have the same meaning, not necessarily the same keywords.

One of the core enabling technologies for LLMs is vector embeddings. While computers cannot directly understand text,
embeddings represent text numerically. All user-provided text is converted to embeddings, which are used to generate
responses.

## Components

Converting text into embedding is a time-consuming process. To avoid that, we have vector databases explicitly designed for efficient storage and retrieval of vector embeddings.

### Vectorize

The most compute intensive step in building an index is vectorization. The path parameter sets the path to the vector
model. There is logic to automatically detect the vector model method but it can also be set directly.

The batch and encodebatch parameters control the vectorization process. Larger values for batch will pass larger batches
to the vectorization method. Larger values for encodebatch will pass larger batches for each vector encode call. In the
case of GPU vector models, larger values will consume more GPU memory.

Data is buffered to temporary storage during indexing as embeddings vectors can be quite large (for example 768
dimensions of float32 is 768 * 4 = 3072 bytes per vector). Once vectorization is complete, a mmapped array is created
with all vectors for Approximate Nearest Neighbor (ANN) indexing.

### index configuration

#### Approximate Nearest Neighbor (ANN)  
for storing vector embeddings.

## Vector Embedding

Vector Embeddings are numerical vector representations of data. They are not only limited to text but can also represent
images, videos, and other types of data. They are usually created using an embedding model such as OpenAI's
text-embedding-ada-002.

## Hypothetical Document Embedding (HyDE)

However, there’s a drawback to this approach as it may not consistently produce good results. For instance, if the subject being discussed is entirely unfamiliar to the language model, this method is not effective and could lead to increased instances of generating incorrect information.

## Models
Making it possible to build retrieval augmented generation (RAG) applications that combine text prompts with existing
documents or other data.

Samples:
- nomic-embed-text (Ollama)
- sentence-transformers (Ollama)
- mistral-text-embeddings (Ollama)
- text-embedding-3-large (OpenAI)
- text-ada-002 (OpenAI)

## Embedding Tools

- OpenAI
- Gemini
- Ollama
- Voyage AI
- Azure OpenAI
- Mistral
- Fireworks
- Together
- HuggingFace
- Qdrant FastEmbed
- IngestAI / embedditor https://github.com/IngestAI/embedditor

## Embedding Databases

Embeddings databases are the engine that delivers semantic search. Data is transformed into embeddings vectors where
similar concepts will produce similar vectors. Indexes both large and small are built with these vectors. The indexes
are used to find results that have the same meaning, not necessarily the same keywords.

### txtai

txtai is an all-in-one embeddings database for semantic search, LLM orchestration and language model workflows.
https://neuml.github.io/txtai/


# Resources

- https://neuml.github.io/txtai/embeddings/
- https://neuml.github.io/txtai/embeddings/methods/
- https://neuml.github.io/txtai/embeddings/indexing/
- https://ollama.com/blog/embedding-models
- https://lancedb.github.io/lancedb/embeddings/default_embedding_functions/