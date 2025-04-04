# Storing

Storage is a necessary component when building user-facing AI products. While agents come with built-in memory, it only
lasts during the active session. For persistent conversations across sessions, Agno provides storage options that work
with individual agents, multi-agent teams and complex workflows.

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

## Articles

### Times and Vector

- https://www.pinecone.io/learn/time-series-vectors/
- https://www.datanami.com/2023/09/25/timescaledb-is-a-vector-database-now-too/
- https://levelup.gitconnected.com/geospatial-vector-search-building-an-ai-powered-geo-aware-news-search-6cbda8919465
- BTW: https://www.timescale.com/learn/vector-search-vs-semantic-search
- https://siliconangle.com/2023/09/25/time-series-database-timescale-adds-vector-search-ai/

### Others

- Vector Search in DBs
- https://clickhouse.com/blog/vector-search-clickhouse-p1 and https://clickhouse.com/blog/vector-search-clickhouse-p2
- https://solr.apache.org/guide/solr/latest/query-guide/dense-vector-search.html
- https://www.elastic.co/de/what-is/vector-search
- https://www.elastic.co/de/enterprise-search/vector-search
- https://github.com/pgvector/pgvector
- https://www.timescale.com/blog/postgresql-as-a-vector-database-create-store-and-query-openai-embeddings-with-pgvector/
