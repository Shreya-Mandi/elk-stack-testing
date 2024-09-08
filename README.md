# elk-stack-testing
Aim: To understand search and log analytics in web applications

Building an elk stack project using:
- open search
- open dashboards

## OpenSearch
- distributed search and analytics
- search by fiels, multiple indexes, rank results by score, sort and aggregate results

- log analytics: feed logs of an application into OpenSearch and use search and visualisation

## Distrubuted design: Clusters and nodes
- nodes: servers that store and process search requests
    - if you have multiple machines you can subdivide responsibilites search and indexing or cluster state management etc based on device specs

## Indices and documents
- each index is a collection of JSON documents
- mappings: a collections of fields a document in teh index must have
- settings: index name, creation date, number of shards

## Primary and replica shards
- shards: splits large indexes into shards
- replicas: for failure and search latency reduction
- rule of thumb is to keep shard size between 10–50 GB.

> being a piece of an OpenSearch index, each shard is actually a full Lucene index—

1. OpenSearch:
OpenSearch is an open-source search and analytics engine, forked from Elasticsearch. It's used for full-text search, structured search, analytics, and more.

2. Index:
In OpenSearch, an index is a collection of documents that have somewhat similar characteristics. It's like a database in a relational database system.

3. Shard:
A shard is a subset of an index. OpenSearch divides indices into shards to distribute data across multiple nodes in a cluster. This allows for horizontal scalability and improved performance.

4. Lucene:
Lucene is a high-performance, full-featured text search engine library written in Java. It's the underlying search library used by OpenSearch.

5. Lucene Index:
A Lucene index is the core data structure that Lucene uses to store and retrieve documents quickly.

Now, to explain the statement:

"Being a piece of an OpenSearch index, each shard is actually a full Lucene index"

This means that while a shard is logically a part of an OpenSearch index, it is implemented as a complete, self-contained Lucene index. Here's why this is significant:

1. Full functionality: Each shard can operate independently, with all the capabilities of a full Lucene index.

2. Scalability: This design allows OpenSearch to distribute these self-contained units (shards) across multiple nodes in a cluster.

3. Performance: Searches can be executed on each shard in parallel, improving overall search performance.

4. Resilience: If one shard goes down, the others can still operate, providing fault tolerance.

This architecture allows OpenSearch to combine the power of Lucene's search capabilities with distributed systems' scalability and resilience.
