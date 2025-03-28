# RAG Retrieval

Retrieval and generation: the actual RAG chain, which takes the user query at run time and retrieves the relevant data
from the index, then passes that to the model.

- Retrieve: Given a user input, relevant splits are retrieved from storage using a Retriever.
- Generate: A ChatModel / LLM produces an answer using a prompt that includes both the question with the retrieved data

## Retriever

A retriever is an interface that returns documents given an unstructured query. It is more general than a vector store.
A retriever does not need to be able to store documents, only to return (or retrieve) them. Retrievers can be created
from vector stores, but are also broad enough to include Wikipedia search and Amazon Kendra.

Retrievers accept a string query as input and return a list of Documents as output.

## Benchmarks

- BEIR is useful for benchmarking if a particular retrieval model generalize well to niche domains in a zero-shot
  setting.

## Evaluation

### Samples
- https://docs.llamaindex.ai/en/stable/examples/evaluation/retrieval/retriever_eval/

# Resources

- https://python.langchain.com/docs/integrations/retrievers/
- https://docs.llamaindex.ai/en/v0.10.19/module_guides/querying/retriever/root.html
