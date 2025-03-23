# RAG (Retrieval-Augmented Generation)
RAG is a framework designed to enhance the performance of generative AI models by integrating external knowledge sources into the generative process. 

## Components

Here’s how it works:

Retrieval Component: This part fetches relevant information from external knowledge bases, databases, or other data repositories. These sources can include structured or unstructured data, such as documents, APIs, or even live data streams.

Augmentation: The retrieved information is used to inform and guide the generative model. This ensures the outputs are more factually accurate, grounded in external data, and contextually rich.

Generation: The generative AI system (like GPT) synthesizes the retrieved knowledge with its own reasoning capabilities to produce final outputs.
RAG is particularly valuable when working with complex queries or domains requiring up-to-date, domain-specific knowledge.

Indexing: a pipeline for ingesting data from a source and indexing it. This usually happens offline.
- Load: First we need to load our data. This is done with Document Loaders.
- Split: Text splitters break large Documents into smaller chunks. This is useful both for indexing data and passing it into a model, as large chunks are harder to search over and won't fit in a model's finite context window.
- Store: We need somewhere to store and index our splits, so that they can be searched over later. This is often done using a VectorStore and Embeddings model.

Retrieval and generation: the actual RAG chain, which takes the user query at run time and retrieves the relevant data from the index, then passes that to the model.
- Retrieve: Given a user input, relevant splits are retrieved from storage using a Retriever.
- Generate: A ChatModel / LLM produces an answer using a prompt that includes both the question with the retrieved data


## Paradigms

### Vector RAG
Traditional RAG or vector RAG runs a vector search to find the top N most relevant matches to a user's input. Those matches are passed to an LLM and the answer is returned.

The query runs a vector search for the best matching documents in the Embeddings index. Those matches are then placed into a LLM prompt. The LLM prompt is executed and the answer is returned.

### Graph RAG
Graph RAG is a new method that uses knowledge or semantic graphs to generate a context. Instead of a vector search, graph path queries are run. Graph RAG in the context of this application supports the following methods to generate context.

### Naive RAG
The Naive RAG research paradigm represents the earliest methodology, which gained prominence shortly after the widespread adoption of ChatGPT. The Naive RAG follows a traditional process that includes indexing, retrieval, and generation, which is also characterized as a “Retrieve-Read” framework.

### Advanced RAG
Advanced RAG introduces specific improvements to overcome the limitations of Naive RAG. Focusing on enhancing retrieval quality, it employs pre-retrieval and post-retrieval strategies. To tackle the indexing issues, Advanced RAG refines its indexing techniques through the use of a sliding window approach, fine-grained segmentation, and the incorporation of metadata.

### Modular RAG
The modular RAG architecture advances beyond the former two RAG paradigms, offering enhanced adaptability and versatility. It incorporates diverse strategies for improving its components, such as adding a search module for similarity searches and refining the retriever through fine-tuning.

## Query types

### Single-Hop Query

A single-hop query is a straightforward question that requires retrieving information from a single document or source to provide a relevant answer. It involves only one step to arrive at the answer.

Example (Specific Query):

    “What year did Albert Einstein publish the theory of relativity?”

This is a specific, fact-based question that can be answered with a single retrieval from a document containing that information.

Example (Abstract Query):

    “How did Einstein’s theory change our understanding of time and space?”

While this query still refers to a single concept (the theory of relativity), it requires a more abstract or interpretive explanation from the source material.


### Multi-Hop Query

A multi-hop query involves multiple steps of reasoning, requiring information from two or more sources. The system must retrieve information from various documents and connect the dots to generate an accurate answer.

Example (Specific Query):

    “Which scientist influenced Einstein’s work on relativity, and what theory did they propose?”

This requires the system to retrieve information about both the scientist who influenced Einstein and the specific theory, potentially from two different sources.

Example (Abstract Query):

    “How have scientific theories on relativity evolved since Einstein’s original publication?”

This abstract query requires the retrieval of multiple pieces of information over time and across different sources to form a broad, interpretive response about the evolution of the theory.


### Specific vs. Abstract Queries in a RAG

    Specific Query: Focuses on clear, fact-based retrieval. The goal in RAG is to retrieve highly relevant information from one or more documents that directly address the specific question.

    Abstract Query: Requires a broader, more interpretive response. In RAG, abstract queries challenge the retrieval system to pull from documents that contain higher-level reasoning, explanations, or opinions, rather than simple facts.

In both single-hop and multi-hop cases, the distinction between specific and abstract queries shapes the retrieval and generation process by determining whether the focus is on precision (specific) or on synthesizing broader ideas (abstract).

Different types of queries requires different contexts to be synthesize. To solve this problem, Ragas uses a Knowledge Graph based approach to Test set Generation.


## Other RAG techniques

### Vanilla RAG
- https://lancedb.github.io/lancedb/rag/vanilla_rag/
- https://colab.research.google.com/github/lancedb/vectordb-recipes/blob/main/tutorials/RAG-from-Scratch/RAG_from_Scratch.ipynb

### Multi-head RAG

### Corrective RAG

### Agentic RAG

### Graph RAG

### Self RAG

### Adaptive RAG

### SFR RAG

### RAG-Fusion


## Research
- https://arxiv.org/abs/2408.02545 (RAG for LLMs)

## Resources
- https://python.langchain.com/docs/tutorials/rag/
- https://www.dataconversionlaboratory.com/post/the-role-of-structured-content-in-rag
- https://techcommunity.microsoft.com/t5/microsoft-developer-community/rag-on-structured-data-with-postgresql/ba-p/4164456
- https://docs.llamaindex.ai/en/stable/ (RAG with LlamaIndex 🦙 - Docling)
- https://blog.kuzudb.com/post/llms-graphs-part-1/
- https://community.openai.com/t/what-ontology-rag-and-graph-data-do-you-use-to-develop-intelligent-assistants/787860/3
- https://ds4sd.github.io/docling/examples/rag_llamaindex/
- https://python.langchain.com/docs/tutorials/rag/
- https://blog.langchain.dev/graph-based-metadata-filtering-for-improving-vector-search-in-rag-applications/ (Graph-based metadata filtering for improving vector search in RAG applications)
- https://www.200ok.ai/blog/rag-vs-tag-a-deep-dive/
- https://cobusgreyling.medium.com/corrective-rag-crag-5e40467099f8
- https://pub.towardsai.net/rag-from-scratch-66c5eff02482
- https://www.ibm.com/think/topics/ai-agents-vs-ai-assistants
- https://buzzdatascience.substack.com/p/ai-agents-vs-llms-vs-ai-assistants?utm_campaign=post&utm_medium=web
- https://medium.com/@jagadeesan.ganesh/mastering-llm-ai-agents-building-and-using-ai-agents-in-python-with-real-world-use-cases-c578eb640e35
