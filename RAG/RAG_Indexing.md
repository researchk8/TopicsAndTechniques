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


# Resources
- https://neuml.github.io/txtai/embeddings/indexing/