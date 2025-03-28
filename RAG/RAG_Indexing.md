# Indexing

a pipeline for ingesting data from a source and indexing it. This usually happens offline.

- Load: First we need to load our data. This is done with Document Loaders.
- Split: Text splitters break large Documents into smaller chunks. This is useful both for indexing data and passing it
  into a model, as large chunks are harder to search over and won't fit in a model's finite context window.
- Store: We need somewhere to store and index our splits, so that they can be searched over later. This is often done
  using a VectorStore and Embeddings model.

## Vectorization

The most compute intensive step in building an index is vectorization. The path parameter sets the path to the vector
model. There is logic to automatically detect the vector model method but it can also be set directly.

The batch and encodebatch parameters control the vectorization process. Larger values for batch will pass larger batches
to the vectorization method. Larger values for encodebatch will pass larger batches for each vector encode call. In the
case of GPU vector models, larger values will consume more GPU memory.

Data is buffered to temporary storage during indexing as embeddings vectors can be quite large (for example 768
dimensions of float32 is 768 * 4 = 3072 bytes per vector). Once vectorization is complete, a mmapped array is created
with all vectors for Approximate Nearest Neighbor (ANN) indexing.

## Chunking

When it comes to RAG systems, you’ll need to pay special attention to how big the individual pieces of data are. How you
divide your data up is called chunking, and it’s more complex than embedding whole documents. 

Chunking is the process of breaking down large pieces of text into smaller segments or chunks. In the context of RAG, embedding smaller chunks instead of entire documents to create the knowledge base means that given a user query, you only have to retrieve the most relevant document chunks, resulting in fewer input tokens and more targeted context for the LLM to work with.

### Chunking strategies

With these concerns in mind, several common chunking strategies have emerged.

- Agentic

#### Recursive Chunking

While Fixed size chunking is easier to implement, it doesn’t consider the structure of text. Recursive chunking offers
an alternative.

In this method, we divide the text into smaller chunk in a hierarchical and iterative manner using a set of separators.
If the initial attempt at splitting the text doesn’t produce chunks of the desired size, the method recursively calls
itself on the resulting chunks with a different separator until the desired chunk size is achieved.

Langchain framework offers RecursiveCharacterTextSplitter class, which splits text using default separators (“\n\n”,
“\n”, “ “,””)

#### ChunkSized

For both of these types, you can apply the chunking method over sliding windows; that is, instead of starting new chunks
at the end of the previous chunk, new chunks overlap the content of the previous one and contain part of it. This can
better capture the context around the edges of each chunk and increase the semantic relevance of your overall system.
The tradeoff is that it requires greater storage requirements and can store redundant information, which can require
extra processing in searches and make it harder for your RAG system to efficiently pull the right source.

##### Fixed Size Chunking

This is the most crude and simplest method of segmenting the text. It breaks down the text into chunks of a specified
number of characters, regardless of their content or structure.

Langchain and llamaindex framework offer CharacterTextSplitter and SentenceSplitter (default to spliting on sentences)
classes for this chunking technique. A few concepts to remember -

    How the text is split: by single character
    How the chunk size is measured: by number of characters
    chunk_size: the number of characters in the chunks
    chunk_overlap: the number of characters that are being overlap in sequential chunks. keep duplicate data across chunks
    separator: character(s) on which the text would be split on (default “”)

##### random chunk sizes

#### Context-aware chunking

Context-aware chunking splits documents based on punctuation like periods, commas, or paragraph breaks or use markdown
or HTML tags if your content contains them. Most text contains these sort of semantic markers that indicate what
characters make up a meaningful chunk, so using them makes a lot of sense.

#### Document Based Chunking

In this chunking method, we split a document based on its inherent structure. This approach considers the flow and
structure of content but may not be as effective documents lacking clear structure.

#### Semantic Chunking

All above three levels deals with content and structure of documents and necessitate maintaining constant value of chunk
size. This chunking method aims to extract semantic meaning from embeddings and then assess the semantic relationship
between these chunks. The core idea is to keep together chunks that are semantic similar.

This adaptively picks the breakpoint in-between sentences using embedding similarity.

few concepts to know

    buffer_size: configurable parameter that decides the initial window for chunks
    breakpoint_percentile_threshold: another configurable parameter. The threshold value to decide where to split the chunk
    embed_mode: the embedding model used.

#### Agentic Chunking

This chunking strategy explore the possibility to use LLM to determine how much and what text should be included in a
chunk based on the context.

After generating propositions, these are being feed to LLM-based agent. This agent determine whether a proposition
should be included in an existing chunk or if a new chunk should be created.

### Chunk overlap
Number of overlapping characters or tokens between chunks; overlapping chunks can help preserve cross-chunk context; the degree of overlap is typically specified as a percentage of the chunk size

### Splitting technique
Determines where the chunk boundaries will be placed — based on paragraph boundaries, programming language-specific separators, tokens, or even semantic boundaries

# Resources

- https://medium.com/@anuragmishra_27746/five-levels-of-chunking-strategies-in-rag-notes-from-gregs-video-7b735895694d
- https://neuml.github.io/txtai/embeddings/indexing/
- https://www.mongodb.com/developer/products/atlas/choosing-chunking-strategy-rag/