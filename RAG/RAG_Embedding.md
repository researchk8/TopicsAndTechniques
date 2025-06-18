# Embedding

Embeddings databases are the engine that delivers semantic search. Data is transformed into embeddings vectors where
similar concepts will produce similar vectors. Indexes both large and small are built with these vectors. The indexes
are used to find results that have the same meaning, not necessarily the same keywords.

One of the core enabling technologies for LLMs is vector embeddings. While computers cannot directly understand text,
embeddings represent text numerically. All user-provided text is converted to embeddings, which are used to generate
responses.

## Components

Converting text into embedding is a time-consuming process. To avoid that, we have vector databases explicitly designed
for efficient storage and retrieval of vector embeddings.

### Vectorize

The most compute intensive step in building an index is vectorization. The path parameter sets the path to the vector
model. There is logic to automatically detect the vector model method but it can also be set directly.

The batch and encodebatch parameters control the vectorization process. Larger values for batch will pass larger batches
to the vectorization method. Larger values for encodebatch will pass larger batches for each vector encode call. In the
case of GPU vector models, larger values will consume more GPU memory.

Data is buffered to temporary storage during indexing as embeddings vectors can be quite large (for example 768
dimensions of float32 is 768 * 4 = 3072 bytes per vector). Once vectorization is complete, a mmapped array is created
with all vectors for Approximate Nearest Neighbor (ANN) indexing.

### index configuration

#### Approximate Nearest Neighbor (ANN)

for storing vector embeddings.

## Vector Embedding

Vector Embeddings are numerical vector representations of data. They are not only limited to text but can also represent
images, videos, and other types of data. Vector embeddings are a way to convert words and sentences and other data into
numbers that capture their meaning and
relationships. They represent different data types as points in a multidimensional space, where similar data points are
clustered closer together. These numerical representations help machines understand and process this data more
effectively.

### Word embedding definition

Word embedding is a technique used in natural language processing (NLP) that represents words as numbers so that a
computer can work with them. It is a popular approach for learned numeric representations of text.

Because machines need assistance with how to deal with words, each word needs to be assigned a number format so it can
be processed. This can be done via a few different approaches:

- One-hot encoding gives each word in a body of text a unique number. This number is turned into a binary vector (using
  0s and 1s) that represents the word.
- Count-based representation counts the number of times a word appears in a body of text and assigns a corresponding
  vector to it.
- SLIM combination utilizes both these methods so that a computer can understand both the meaning of the words and how
  often they appear in the text.

Word embedding creates a high-dimensional space where each word is assigned a dense vector (more on this below) of
numbers. A computer can then use these vectors to understand the relationships between words and make predictions.

Word embeddings are used to enable vector search. They are foundational for natural language processing tasks such as
sentiment analysis, text classification, and language translation. Word embeddings provide an effective path for
machines to recognize and capture the semantic relationships between words. This makes NLP models more accurate and
efficient than with manual feature engineering. Thus, the end result is more accessible and effective to users.

#### How are word embeddings made?

Word embeddings can be made using a variety of techniques.

- Word2vec is a two-layer neural network-based algorithm that inputs a text corpus and outputs a set of vectors (hence
  the name). A commonly used Word2vec example is "King – Man + Woman = Queen." By deducing the relationship between "
  King" and "Man," and between "Man" and "Woman," the algorithm can identify "Queen" as the appropriate corresponding
  word to "King." Word2vec is trained using either Skip-Gram or Continuous Bag of Words (CBOW) algorithms. Skip-Gram
  tries to predict context words from a target word. Continuous Bag of Words functions the opposite way, predicting the
  target word using the context of the words around it.
- GloVe (Global Vectors) is based on the idea that the meaning of a word can be inferred from its co-occurrence with
  other words in a corpus of text. The algorithm creates a co-occurrence matrix that captures how frequently words
  appear together in the corpus.
- fasText is an extension of the Word2vec model and is based on the idea of representing words as a bag of character
  n-grams, or sub-word units, instead of just as individual words. Using a model similar to Skip-Gram, fasText captures
  information about the internal structure of words that helps it process new and unfamiliar vocabulary.
- ELMo (Embeddings from Language Models) differs from word embeddings like the ones mentioned above because it uses a
  deep neural network that analyzes the entire context in which the word appears. This allows it to pick up on subtle
  nuances in meaning that other embedding techniques may not catch.
- TF-IDF (Term Frequency - Inverse Document Frequency) is a mathematical value determined by multiplying the Term
  Frequency (TF) with the Inverse Document Frequency (IDF). The TF refers to the ratio of the target terms in the
  document compared to the total terms in the document. The IDF is a logarithm of the ratio of the total documents to
  the number of documents containing the target term.

## Hypothetical Document Embedding (HyDE)

However, there’s a drawback to this approach as it may not consistently produce good results. For instance, if the
subject being discussed is entirely unfamiliar to the language model, this method is not effective and could lead to
increased instances of generating incorrect information.

## Models

Making it possible to build retrieval augmented generation (RAG) applications that combine text prompts with existing
documents or other data.

Samples:

- Word2Vec
- GTE-Base
- RoBERTa
- MPNet V2

## Embedding Databases

Embeddings databases are the engine that delivers semantic search. Data is transformed into embeddings vectors where
similar concepts will produce similar vectors. Indexes both large and small are built with these vectors. The indexes
are used to find results that have the same meaning, not necessarily the same keywords.

# Resources

- https://www.elastic.co/what-is/vector-embedding
- https://www.elastic.co/what-is/word-embedding
- https://neuml.github.io/txtai/embeddings/
- https://neuml.github.io/txtai/embeddings/methods/
- https://neuml.github.io/txtai/embeddings/indexing/
- https://ollama.com/blog/embedding-models
- https://lancedb.github.io/lancedb/embeddings/default_embedding_functions/