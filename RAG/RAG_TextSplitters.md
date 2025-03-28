# Text Splitters

Document splitting is often a crucial preprocessing step for many applications. It involves breaking down large texts
into smaller, manageable chunks. This process offers several benefits, such as ensuring consistent processing of varying
document lengths, overcoming input size limitations of models, and improving the quality of text representations used in
retrieval systems. There are several strategies for splitting documents, each with its own advantages.

Text splitters split documents into smaller chunks for use in downstream applications.

There are several reasons to split documents:

- Handling non-uniform document lengths: Real-world document collections often contain texts of varying sizes. Splitting
  ensures consistent processing across all documents.
- Overcoming model limitations: Many embedding models and language models have maximum input size constraints. Splitting
  allows us to process documents that would otherwise exceed these limits.
- Improving representation quality: For longer documents, the quality of embeddings or other representations may degrade
  as they try to capture too much information. Splitting can lead to more focused and accurate representations of each
  section.
- Enhancing retrieval precision: In information retrieval systems, splitting can improve the granularity of search
  results, allowing for more precise matching of queries to relevant document sections.
- Optimizing computational resources: Working with smaller chunks of text can be more memory-efficient and allow for
  better parallelization of processing tasks.

## Approaches

### Length-based

The most intuitive strategy is to split documents based on their length. This simple yet effective approach ensures that
each chunk doesn't exceed a specified size limit. Key benefits of length-based splitting:

    Straightforward implementation
    Consistent chunk sizes
    Easily adaptable to different model requirements

Types of length-based splitting:

    Token-based: Splits text based on the number of tokens, which is useful when working with language models.
    Character-based: Splits text based on the number of characters, which can be more consistent across different types of text.

### Text-structured based

Text is naturally organized into hierarchical units such as paragraphs, sentences, and words. We can leverage this
inherent structure to inform our splitting strategy, creating split that maintain natural language flow, maintain
semantic coherence within split, and adapts to varying levels of text granularity. LangChain's
RecursiveCharacterTextSplitter implements this concept:

    The RecursiveCharacterTextSplitter attempts to keep larger units (e.g., paragraphs) intact.
    If a unit exceeds the chunk size, it moves to the next level (e.g., sentences).
    This process continues down to the word level if necessary.

### Document-structured based

Some documents have an inherent structure, such as HTML, Markdown, or JSON files. In these cases, it's beneficial to
split the document based on its structure, as it often naturally groups semantically related text. Key benefits of
structure-based splitting:

    Preserves the logical organization of the document
    Maintains context within each chunk
    Can be more effective for downstream tasks like retrieval or summarization

Examples of structure-based splitting:

    Markdown: Split based on headers (e.g., #, ##, ###)
    HTML: Split using tags
    JSON: Split by object or array elements
    Code: Split by functions, classes, or logical blocks

#### Semantic meaning based

Unlike the previous methods, semantic-based splitting actually considers the content of the text. While other approaches
use document or text structure as proxies for semantic meaning, this method directly analyzes the text's semantics.
There are several ways to implement this, but conceptually the approach is split text when there are significant changes
in text meaning. As an example, we can use a sliding window approach to generate embeddings, and compare the embeddings
to find significant differences:

    Start with the first few sentences and generate an embedding.
    Move to the next group of sentences and generate another embedding (e.g., using a sliding window approach).
    Compare the embeddings to find significant differences, which indicate potential "break points" between semantic sections.

This technique helps create chunks that are more semantically coherent, potentially improving the quality of downstream
tasks like retrieval or summarization.

### Token based

Splits text on tokens. There exist a few different ways to measure tokens.

## Input types

- FileBased
- UrlBased
- ApplicationBased

## Tools

- https://www.chunkviz.com/

# Resources

- https://python.langchain.com/docs/concepts/text_splitters/