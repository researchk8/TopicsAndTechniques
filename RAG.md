# RAG (Retrieval-Augmented Generation)
RAG is a framework designed to enhance the performance of generative AI models by integrating external knowledge sources into the generative process. Here’s how it works:

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


## Tools
- https://github.com/pgvector/pgvector-python
- https://github.com/fsndzomga/rag_nebius_postgresql ()
- https://github.com/NirDiamant/RAG_TECHNIQUES ()
- https://github.com/infiniflow/ragflow (RAGFlow is an open-source RAG (Retrieval-Augmented Generation) engine based on deep document understanding. )
- https://github.com/Thytu/Agentarium
- AdvancedRAG
- RAG4LLM: Gao

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

## Benchmarks
- Natural Questions (NQ)
- HotpotQA (HPQA)
- TriviaQA 
- HaluEvalQA 
- TruthfulQA
- FreshQA
- FinanceBench

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
