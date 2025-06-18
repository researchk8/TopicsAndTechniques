# KnowledgeGraph

A opens in new tabknowledge graph is an organized representation of real-world entities and their relationships. It is
typically stored in a graph database, which natively stores the relationships between data entities. Entities in a
knowledge graph can represent objects, events, situations, or concepts. The relationships between these entities capture
the context and meaning of how they are connected.

Knowledge graphs are typically made up of datasets from various sources, which frequently differ in structure. Schemas,
identities and context work together to provide structure to diverse data. Schemas provide the framework for the
knowledge graph, identities classify the underlying nodes appropriately, and the context determines the setting in which
that knowledge exists. These components help distinguish words with multiple meanings.

## Components

### Nodes

Nodes denote and store details about entities, such as people, places, objects, or institutions. Each node has a (or
sometimes several) label to identify the node type and may optionally have one or more properties (attributes). Nodes
are also sometimes called vertices.

### Relationships

Relationships link two nodes together: they show how the entities are related. Like nodes, each relationship has a label
identifying the relationship type and may optionally have one or more properties. Relationships are also sometimes
called edges.

### Organizing Principle(s)

Organizing Principles are a framework, or schema, that organizes nodes and relationships according to fundamental
concepts essential to the use cases at hand. Unlike many data designs, knowledge graphs easily incorporate multiple
organizing principles.

Organizing principles range from simple (product line -> product category -> product taxonomy) to complex (a complete
business vocabulary that explains the data in the graph). Think of an organizing principle as a conceptual map or
metadata layer overlaying the data and relationships in the graph.

The model uses the same node-and-relationship structure as the rest of the knowledge graph to describe the organizing
principles – which means you can write queries that draw from both instance data and organizing principles.

## Benefits

One of the benefits of knowledge graphs is that you can infer patterns and relations from the data in the graph.
Semantic reasoning allows you to define rules within the knowledge graph which will automatically apply to the
underlying data.

Two aspects of semantic search, faceted and cross-domain search, are empowered by knowledge graphs for applying context
to user queries through the investigation of relevant relationships.

With faceted search, users are able to distil what they need from a query by looking at the categories created by a
knowledge graph. Similarly, cross-domain search uses relationships to integrate outputs from a variety of resources.

## Building a Knowledge Graph

Creating a Knowledge Graph involves several steps:

- Data Collection: Gathering structured and unstructured data from various sources.
- Data Integration: Combining data from different sources, resolving conflicts, and ensuring consistency.
- Entity Resolution: Identifying and linking different representations of the same entity.
- Graph Construction: Defining entities, relationships, and properties to create the graph structure.
- Enrichment: Adding additional information and context to the entities and relationships.
- Querying and Analysis: Using graph queries and algorithms to extract insights and knowledge.

## Advantages of Knowledge Graphs

Knowledge Graphs offer several advantages over traditional databases and information management systems:

- Flexibility: They can easily incorporate new types of information and relationships without requiring a predefined
  schema.
- Contextual Understanding: They provide a rich context for entities, enabling more accurate interpretation of data.
- Interconnectivity: They highlight the connections between disparate pieces of information, revealing insights that
  might not be apparent in isolated data.
- Enhanced Search and Discovery: They improve search capabilities by considering the semantic relationships between
  entities.
- Scalability: They can handle large volumes of data and complex queries efficiently.

## Challenges with Knowledge Graphs

While Knowledge Graphs are powerful tools, they also come with challenges:

- Data Quality: The usefulness of a Knowledge Graph is highly dependent on the accuracy and quality of the underlying
  data.
- Integration: Integrating data from multiple sources can be complex and time-consuming.
- Maintenance: Keeping the Knowledge Graph up-to-date requires continuous effort and resources.
- Complexity: Designing and querying Knowledge Graphs can be complex and may require specialized expertise.

# Resources

- https://www.ibm.com/think/topics/knowledge-graph
- https://neo4j.com/blog/knowledge-graph/what-is-knowledge-graph/
- https://deepai.org/machine-learning-glossary-and-terms/knowledge-graph