# Chunking

When it comes to RAG systems, you’ll need to pay special attention to how big the individual pieces of data are. How you
divide your data up is called chunking, and it’s more complex than embedding whole documents.

Chunking is the process of breaking down large pieces of text into smaller segments or chunks. In the context of RAG,
embedding smaller chunks instead of entire documents to create the knowledge base means that given a user query, you
only have to retrieve the most relevant document chunks, resulting in fewer input tokens and more targeted context for
the LLM to work with.

With these concerns in mind, several common chunking strategies have emerged.

## Recursive Chunking

Recursive chunking is a method of splitting documents into smaller chunks by recursively applying a chunking strategy.
This is useful when you want to process large documents in smaller, manageable pieces.

While Fixed size chunking is easier to implement, it doesn’t consider the structure of text. Recursive chunking offers
an alternative.

In this method, we divide the text into smaller chunk in a hierarchical and iterative manner using a set of separators.
If the initial attempt at splitting the text doesn’t produce chunks of the desired size, the method recursively calls
itself on the resulting chunks with a different separator until the desired chunk size is achieved.

Parameters:

- chunk_size: The maximum size of each chunk.
- overlap: The number of characters to overlap between chunks.

## Fixed Size Chunking

This is the most crude and simplest method of segmenting the text. It breaks down the text into chunks of a specified
number of characters, regardless of their content or structure.

Langchain and llamaindex framework offer CharacterTextSplitter and SentenceSplitter (default to spliting on sentences)
classes for this chunking technique.

A few concepts to remember:

- How the text is split: by single character
- How the chunk size is measured: by number of characters

Parameters:

- chunk_size: the number of characters in the chunks
- chunk_overlap: the number of characters that are being overlap in sequential chunks. keep duplicate data across chunks
- separator: character(s) on which the text would be split on (default “”)

## Context-aware chunking

Context-aware chunking splits documents based on punctuation like periods, commas, or paragraph breaks or use markdown
or HTML tags if your content contains them. Most text contains these sort of semantic markers that indicate what
characters make up a meaningful chunk, so using them makes a lot of sense.

## Document Based Chunking

Document chunking is a method of splitting documents into smaller chunks based on document structure like paragraphs and
sections. It analyzes natural document boundaries rather than splitting at fixed character counts. This is useful when
you want to process large documents while preserving semantic meaning and context.

In this chunking method, we split a document based on its inherent structure. This approach considers the flow and
structure of content but may not be as effective documents lacking clear structure.

Parameters:

- chunk_size: The maximum size of each chunk.
- overlap: The number of characters to overlap between chunks.

## Semantic Chunking

Semantic chunking is a method of splitting documents into smaller chunks by analyzing semantic similarity between text
segments using embeddings. It uses the chonkie library to identify natural breakpoints where the semantic meaning
changes significantly, based on a configurable similarity threshold. This helps preserve context and meaning better than
fixed-size chunking by ensuring semantically related content stays together in the same chunk, while splitting occurs at
meaningful topic transitions.

All above three levels deals with content and structure of documents and necessitate maintaining constant value of chunk
size. This chunking method aims to extract semantic meaning from embeddings and then assess the semantic relationship
between these chunks. The core idea is to keep together chunks that are semantic similar.

This adaptively picks the breakpoint in-between sentences using embedding similarity.

A few concepts to know:

- buffer_size: configurable parameter that decides the initial window for chunks
- breakpoint_percentile_threshold: another configurable parameter. The threshold value to decide where to split the
  chunk
- embed_mode: the embedding model used.

Parameters:

- embedder: The embedder to use for semantic chunking.
- chunk_size: The maximum size of each chunk.
- similarity_threshold: The similarity threshold for determining chunk boundaries.

## Agentic Chunking

Agentic chunking is an intelligent method of splitting documents into smaller chunks by using a model to determine
natural breakpoints in the text. Rather than splitting text at fixed character counts, it analyzes the content to find
semantically meaningful boundaries like paragraph breaks and topic transitions.

This chunking strategy explore the possibility to use LLM to determine how much and what text should be included in a
chunk based on the context.

After generating propositions, these are being feed to LLM-based agent. This agent determine whether a proposition
should be included in an existing chunk or if a new chunk should be created.

Parameters:

- model: The model to use for chunking.
- max_chunk_size: The maximum size of each chunk.

## Components

### Chunk overlap

Number of overlapping characters or tokens between chunks; overlapping chunks can help preserve cross-chunk context; the
degree of overlap is typically specified as a percentage of the chunk size

### Splitting technique

Determines where the chunk boundaries will be placed — based on paragraph boundaries, programming language-specific
separators, tokens, or even semantic boundaries

# Resources

- https://medium.com/@anuragmishra_27746/five-levels-of-chunking-strategies-in-rag-notes-from-gregs-video-7b735895694d
- https://neuml.github.io/txtai/embeddings/indexing/
- https://www.mongodb.com/developer/products/atlas/choosing-chunking-strategy-rag/