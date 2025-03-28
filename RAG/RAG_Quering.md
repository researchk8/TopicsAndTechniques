# RAG Querying

A query engine is an end-to-end flow that allows you to ask questions over your data. It takes in a natural language
query, and returns a response, along with reference context retrieved and passed to the LLM.

Query engine is a generic interface that allows you to ask question over your data. A query engine takes in a natural
language query, and returns a rich response. It is most often (but not always) built on one or many indexes via
retrievers. You can compose multiple query engines to achieve more advanced capability.

## Query translation

Natural language queries with filters can be converted to txtai-compatible SQL statements with query translation.

For example:
- can be converted to a SQL statement with a similar clause and date filter.

This requires setting a query translation model. The default query translation model is t5-small-txtsql but this can
easily be finetuned to handle different use cases.

### Hybrid search

When an embeddings database has both a sparse and dense index, both indexes will be queried and the results will be
equally weighted unless otherwise specified.

### Graph search

If an embeddings database has an associated graph network, graph searches can be run. The search syntax below uses
openCypher.

### Vector search
Vectors can be indexed by using algorithms such as hierarchical navigable small world (HNSW), locality-sensitive hashing (LSH) or product quantization (PQ).

### Keyword search

### graph query language GQL

## Query types

### Single-Hop Query

A single-hop query is a straightforward question that requires retrieving information from a single document or source
to provide a relevant answer. It involves only one step to arrive at the answer.

Example (Specific Query):

    “What year did Albert Einstein publish the theory of relativity?”

This is a specific, fact-based question that can be answered with a single retrieval from a document containing that
information.

Example (Abstract Query):

    “How did Einstein’s theory change our understanding of time and space?”

While this query still refers to a single concept (the theory of relativity), it requires a more abstract or
interpretive explanation from the source material.

### Multi-Hop Query

A multi-hop query involves multiple steps of reasoning, requiring information from two or more sources. The system must
retrieve information from various documents and connect the dots to generate an accurate answer.

Example (Specific Query):

    “Which scientist influenced Einstein’s work on relativity, and what theory did they propose?”

This requires the system to retrieve information about both the scientist who influenced Einstein and the specific
theory, potentially from two different sources.

Example (Abstract Query):

    “How have scientific theories on relativity evolved since Einstein’s original publication?”

This abstract query requires the retrieval of multiple pieces of information over time and across different sources to
form a broad, interpretive response about the evolution of the theory.

### Specific vs. Abstract Queries in a RAG

    Specific Query: Focuses on clear, fact-based retrieval. The goal in RAG is to retrieve highly relevant information from one or more documents that directly address the specific question.

    Abstract Query: Requires a broader, more interpretive response. In RAG, abstract queries challenge the retrieval system to pull from documents that contain higher-level reasoning, explanations, or opinions, rather than simple facts.

In both single-hop and multi-hop cases, the distinction between specific and abstract queries shapes the retrieval and
generation process by determining whether the focus is on precision (specific) or on synthesizing broader ideas (
abstract).

Different types of queries requires different contexts to be synthesize. To solve this problem, Ragas uses a Knowledge
Graph based approach to Test set Generation.

### Graph query tools

- https://github.com/opencypher/openCypher (Specification of the Cypher property graph query language)

## Query Evaluation

Against annotated datasets, whether your own data or an academic benchmark, there are a number of standard metrics that
it helps to be aware of:

- Exact Match (EM): The percentage of queries that are answered exactly correctly.
- Recall: The percentage of queries that are answered correctly, regardless of the number of answers returned.
- Precision: The percentage of queries that are answered correctly, divided by the number of answers returned.
- F1: The F1 score is the harmonic mean of precision and recall. It thus symmetrically represents both precision and
  recall in one metric, considering both false positives and false negatives.

### Query Evaluation Datasets

Datasets that areuseful for evaluating queries that require multiple retrieval steps.

- Natural Questions (NQ)
- HotpotQA (HPQA)
- TriviaQA
- HaluEvalQA
- TruthfulQA
- FreshQA
- FinanceBench

# Resources

- https://neuml.github.io/txtai/embeddings/configuration/database#query
- https://neuml.github.io/txtai/embeddings/query/#query-translation
- https://docs.llamaindex.ai/en/v0.10.19/module_guides/indexing/indexing.html
- https://docs.llamaindex.ai/en/v0.10.19/module_guides/querying/retriever/root.html