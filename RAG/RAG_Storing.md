# Storing

Storage is a necessary component when building user-facing AI products. While agents come with built-in memory, it only lasts during the active session. For persistent conversations across sessions, Agno provides storage options that work with individual agents, multi-agent teams and complex workflows.

## Vector stores

One of the most common ways to store and search over unstructured data is to embed it and store the resulting embedding
vectors, and then at query time to embed the unstructured query and retrieve the embedding vectors that are 'most
similar' to the embedded query. A vector store takes care of storing embedded data and performing vector search for you.
A key part of working with vector stores is creating the vector to put in them, which is usually created via embeddings.
Therefore, it is recommended that you familiarize yourself with the text embedding model interfaces before diving into
this.

## Searching

### Similarity search

### Maximum marginal relevance search (MMR)

Maximal marginal relevance optimizes for similarity to query and diversity among selected documents.

### Hybrid Search

### Multi-Vector-Search