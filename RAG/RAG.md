# RAG (Retrieval-Augmented Generation)

RAG is a framework designed to enhance the performance of generative AI models by integrating external knowledge sources
into the generative process.

Retrieval-Augmented Generation (or RAG) is an architecture used to help large language models like GPT-4 provide better
responses by using relevant information from additional sources and reducing the chances that an LLM will leak sensitive
data, or ‘hallucinate’ incorrect or misleading information.

## Components

Retrieval Component: This part fetches relevant information from external knowledge bases, databases, or other data
repositories. These sources can include structured or unstructured data, such as documents, APIs, or even live data
streams.

Augmentation: The retrieved information is used to inform and guide the generative model. This ensures the outputs are
more factually accurate, grounded in external data, and contextually rich.

Generation: The generative AI system (like GPT) synthesizes the retrieved knowledge with its own reasoning capabilities
to produce final outputs.

RAG is particularly valuable when working with complex queries or domains requiring up-to-date, domain-specific
knowledge.

## Paradigms

### Vector RAG

Traditional RAG or vector RAG runs a vector search to find the top N most relevant matches to a user's input. Those
matches are passed to an LLM and the answer is returned.

The query runs a vector search for the best matching documents in the Embeddings index. Those matches are then placed
into a LLM prompt. The LLM prompt is executed and the answer is returned.

### Graph RAG

Graph RAG is a new method that uses knowledge or semantic graphs to generate a context. Instead of a vector search,
graph path queries are run. Graph RAG in the context of this application supports the following methods to generate
context.

### Naive RAG

The Naive RAG research paradigm represents the earliest methodology, which gained prominence shortly after the
widespread adoption of ChatGPT. The Naive RAG follows a traditional process that includes indexing, retrieval, and
generation, which is also characterized as a “Retrieve-Read” framework.

### Advanced RAG

Advanced RAG introduces specific improvements to overcome the limitations of Naive RAG. Focusing on enhancing retrieval
quality, it employs pre-retrieval and post-retrieval strategies. To tackle the indexing issues, Advanced RAG refines its
indexing techniques through the use of a sliding window approach, fine-grained segmentation, and the incorporation of
metadata.

### Modular RAG

The modular RAG architecture advances beyond the former two RAG paradigms, offering enhanced adaptability and
versatility. It incorporates diverse strategies for improving its components, such as adding a search module for
similarity searches and refining the retriever through fine-tuning.

### Vanilla RAG

- https://lancedb.github.io/lancedb/rag/vanilla_rag/
- https://colab.research.google.com/github/lancedb/vectordb-recipes/blob/main/tutorials/RAG-from-Scratch/RAG_from_Scratch.ipynb

### Multi-head RAG

### Corrective RAG

### Agentic RAG

### Self-Reflective RAG

### Adaptive RAG

### SFR RAG

### Speculative RAG

### RAG-Fusion

### Seld-Route RAG

## Tools

- https://github.com/superlinear-ai/raglite


## Research

- https://arxiv.org/abs/2408.02545 (RAG for LLMs)

## Resources
- https://github.com/aishwaryanr/awesome-generative-ai-guide/blob/main/research_updates/rag_research_table.md
- https://python.langchain.com/docs/tutorials/rag/
- https://www.dataconversionlaboratory.com/post/the-role-of-structured-content-in-rag
- https://techcommunity.microsoft.com/t5/microsoft-developer-community/rag-on-structured-data-with-postgresql/ba-p/4164456
- https://docs.llamaindex.ai/en/stable/ (RAG with LlamaIndex 🦙 - Docling)
- https://blog.kuzudb.com/post/llms-graphs-part-1/
- https://community.openai.com/t/what-ontology-rag-and-graph-data-do-you-use-to-develop-intelligent-assistants/787860/3
- https://ds4sd.github.io/docling/examples/rag_llamaindex/
- https://python.langchain.com/docs/tutorials/rag/
- https://blog.langchain.dev/graph-based-metadata-filtering-for-improving-vector-search-in-rag-applications/ (
  Graph-based metadata filtering for improving vector search in RAG applications)
- https://www.200ok.ai/blog/rag-vs-tag-a-deep-dive/
- https://cobusgreyling.medium.com/corrective-rag-crag-5e40467099f8
- https://pub.towardsai.net/rag-from-scratch-66c5eff02482
- https://www.ibm.com/think/topics/ai-agents-vs-ai-assistants
- https://buzzdatascience.substack.com/p/ai-agents-vs-llms-vs-ai-assistants?utm_campaign=post&utm_medium=web
- https://medium.com/@jagadeesan.ganesh/mastering-llm-ai-agents-building-and-using-ai-agents-in-python-with-real-world-use-cases-c578eb640e35
- https://www.analyticsvidhya.com/blog/2025/01/agentic-rag-system-architectures/
- https://docs.llamaindex.ai/en/stable/understanding/rag/