# Student: Jeorval Jose Cano Morales
## Chapter 2: Data models and Query language
### 1. What is sql?
it is a type of programming language that helps to solve specific problems or problems related to the definition, manipulation and integrity of the information represented by the data that is stored in the databases.

Some aspects of SQL are based on relational calculus, some on relational algebra that comes from the relational model, and some to neither, but are part of SQL.

Because SQL offers an implementation for relational database systems, it is expected to have characteristics similar to those mentioned for the relational model.

For the storage and manipulation operations of the data, the relational model establishes the use of relation and relation variable; meanwhile SQL makes use of tables as a fundamental element.

### 2. What are some reasons to change to NoSQL?
* The need for greater scalability than relational databases, including
very large data sets or very high write performance
* A widespread preference for free and open-source software over commercial
database products
* Specialized query operations that are not compatible with the relational model.
* Frustration with restriction of relational schemas, and a desire for more dynamic and expressive data model

### 3. Why using ID is so important ?

When you use an ID, the information that is meaningful to humans is stored in only one place, and everything that refers to it uses an ID . When you store the text directly, you are duplicating the human-meaningful information in every record that uses it.

### 4. How does relational model works? 
There are no labyrinthine nested structures, no complicated access paths to follow if you want to look at the data. In a relational database, the query optimizer automatically 
decides which parts of the query to execute in which order, and which indexes to use. Those choices are effectively the access path, but the big difference is that they are 
made automatically by the query optimizer, not by the application developer, so we rarely need to think about them. If you want to query your data in new ways, 
you can just declare a new index, and queries will automatically use whichever indexes are most appropriate.

### 5. What are some porperties of the graphs?

Vertex:
* A unique identifier
* A set of outgoing edges
* A set of incoming edges
* A collection of properties (key-value pairs)

Nodes:
* A unique identifier
* The vertex at which the edge starts (the tail vertex)
* The vertex at which the edge ends (the head vertex)
* A label to describe the kind of relationship between the two vertices
* A collection of properties (key-value pairs)

### 6. What are some characteristic of the graph model?
1. Any vertex can have a border connecting it to any other vertex. There is no schema that restricts what types of things may or may not be associated.
1. Given any vertex, you can efficiently find its leading and trailing edges, and thus traverse the graph, that is, follow a path through a chain of vertices, both forward and backward.
1. By using different labels for different types of relationships, you can store several different types of information in a single graph, while maintaining a clean data model.

### 7. What are the two types of NoSQL databases?

1. Document databases address use cases where data comes in self-contained documents and the relationships between one document and another are rare.
1. Graphics databases go in the opposite direction, targeting use cases where anything is potentially related to everything.
