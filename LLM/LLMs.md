## LLMs


## Architectures

### Transformer Architectures
LLMs are based on transformer architectures. The underlying transformer is made up of encoder-decoder layers. 


#### Dense Transformer
The encoder stack consists of layers each of which encodes the input, normalizes it, carries out Multihead attention (to identify contextual dependencies), and then passes these vectors through a fully connected network until the output of the final ecoder layer is concatenated to the decoder input. The decoder stack consists of another set of feed-forward networks responsible for next-token prediction.

Increasing the model’s size improves the output quality. However as evident due to the quadratic complexity of multi-head attention, scaling the traditional dense transformer architecture may be compute-costly for a given number of parameters.

#### MoE Transformer
MoE architecture allows increasing the model’s size and in effect the output quality and inference speed while keeping the compute cost fixed. Instead of dense transformer layers, an MoE uses sparse FFN layers (aka experts) and a gate network (router) to determine which tokens are sent to each expert, usually, top-k experts are selected.

#### Sparse Transformer


#### Hybrid-MoE Transformer

The more expert choices an MoE has, the higher the quality, however, it’s inefficient due to high all-to-all communication overheads. Hybrid-MoE overlaps this communication by combining a residual MoE with a dense transformer, making training faster.

A typical MoE for a batch size of 1 can undergo enough latency just to read the active parameters. In contrast, a Hybrid-MoE can be a lot more efficient than equivalent vanilla MoEs or a Dense transformer. Also, Hybrid-MoEs are capable of handling larger batch sizes for faster inference as well.

## Types

### Autoencoder-Based Model
One type of large language model is the autoencoder-based model, which works by encoding input text into a lower-dimensional representation and then generating new text based on that representation. This type of model is especially good for tasks like summarizing text or generating content.

### Sequence-to-Sequence Model
Another type of large language model is the sequence-to-sequence model, which takes an input sequence (like a sentence) and generates an output sequence (like a translation into another language). These models are often used for machine translation and text summarization.

### Transformer-Based Models
Transformer-based models are another popular type of large language model. These models use a neural network architecture that's great at understanding long-range dependencies in text data, making them useful for a wide range of language tasks, including generating text, translating languages, and answering questions.

### Recursive Neural Network Models
Recursive neural network models are designed to handle structured data like parse trees, which represent the syntactic structure of a sentence. These models are useful for tasks like sentiment analysis and natural language inference.

### Hierarchical Models
Finally, hierarchical models are designed to handle text at different levels of granularity, such as sentences, paragraphs, and documents. These models are used for tasks like document classification and topic modeling.



## Finetuning methods

### Research
https://arxiv.org/pdf/2303.15647


### Adapters

### Resources
- https://magazine.sebastianraschka.com/p/finetuning-llms-with-adapters
- https://magazine.sebastianraschka.com/p/finetuning-large-language-models

## Problems

### Lack of specific information

### Hallucinations

### Generic responses


## Special
## KG in LLMS
- https://www.llamaindex.ai/blog/introducing-the-property-graph-index-a-powerful-new-way-to-build-knowledge-graphs-with-llms (Introducing the Property Graph Index: A Powerful New Way to Build Knowledge Graphs with LLMs — LlamaIndex - Build Knowledge Assistants over your Enterprise Data)
- https://github.com/tomasonjo/blogs/blob/master/llm/graph_based_prefiltering.ipynb (blogs/llm/graph_based_prefiltering.ipynb at master · tomasonjo/blogs · GitHub)

## Frameworks

### Langchain
LangChain is a framework for developing applications powered by large language models (LLMs).
https://github.com/langchain-ai/langchain
https://langchain-ai.github.io/langgraph/

### Vellum
https://www.vellum.ai/

### Rivet
https://rivet.ironcladapp.com/

### Amazon Bedrock's
https://aws.amazon.com/bedrock/agents/

# Surveys
- The official GitHub page for the survey paper "A Survey on Large Language Models for Code Generation". https://github.com/juyongjiang/CodeLLMSurvey


# Resources
- https://medium.com/the-modern-scientist/large-language-models-a-calculator-for-words-7ab4099d0cc9
- https://medium.com/@zaiinn440/moe-vs-dense-vs-hybrid-llm-architectures-9db18428dbe2