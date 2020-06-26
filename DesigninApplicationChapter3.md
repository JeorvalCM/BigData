# What is a hash index?
A hash index is an array of N buckets or slots, each one containing a pointer to a row. Hash indexes use a hash function F(K, N) in which given a key K and the number of buckets N , the function maps the key to the corresponding bucket of the hash index. I want to emphasize that the buckets do not store the keys or its hashed value. They only store the memory address in which the data is placed.

# What is a hash function?
A hash function is any algorithm that maps data of variable length to data of a fixed length in a deterministic and close to random way.

# What is an inverted index?
- In computer science, an inverted index (also referred to as a postings file or inverted file) is a database index storing a mapping from content, such as words or numbers, to its locations in a table, or in a document or a set of documents (named in contrast to a forward index, which maps from documents to content).

# What is a SSTable?
- SSTable (engl. Sorted Strings Table) is a file of key/value string pairs, sorted by keys.

- An SSTable provides a persistent,ordered immutable map from keys to values, where both keys and values are arbitrary byte strings.

# When is it favorable to use an SStable?
- SSTables are best for use case that entail humongous writes are order of magnitude larger than the reads. For example, if you are building a distributed log service, then you would need a storage engine that can take a very large throughput of application and error logs by a wide variety of clients. While the writes have to be o(1), the logs themselves would be sparingly accessed such as for debugging purpose only, so a slightly slower reads would be acceptable (k*log(n) where k=no of segments)

# What does mean LSMtree and what is it?
In computer science, the log-structured merge-tree (or LSM tree) is a data structure with performance characteristics that make it attractive for providing indexed access to files with high insert volume, such as transactional log data. LSM trees, like other search trees, maintain key-value pairs. LSM trees maintain data in two or more separate structures, each of which is optimized for its respective underlying storage medium; data is synchronized between the two structures efficiently, in batches.

# What is a B-Tree?
B-tree is a self-balancing tree data structure that maintains sorted data and allows searches, sequential access, insertions, and deletions in logarithmic time. The B-tree generalizes the binary search tree, allowing for nodes with more than two children.[2] Unlike other self-balancing binary search trees, the B-tree is well suited for storage systems that read and write relatively large blocks of data, such as discs. It is commonly used in databases and file systems.
