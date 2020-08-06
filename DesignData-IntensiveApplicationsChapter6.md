# What is a fixed partition and a dynamic partition?
- Fixed Partition: The first attempt to enable multiprogramming was the creation of fixed or static partitions, in main memory, a partition for each task. The partition size was specified when powering up the system, each partition could be reconfigured by powering up the system again or rebooting the system.
This scheme introduced an essential factor, the protection of memory space for the task. Once a partition was assigned to a task, no other tasks were allowed to enter its borders. This partition scheme is more flexible than the single-user one, since it allows several programs to be in memory at the same time.
- Dynamic Partition

# Why is rebalancing important?
Rebalancing is useful or even necessary after you perform one of the following operations:

- Change the size of the cluster by adding or removing nodes.
- Mark one or more nodes as ephemeral in preparation of removing them from the cluster.
- Change the scaling factor of an elastic cluster, which determines the number of storage containers used to store a projection across the database.
- Set the control node size or realign control nodes on a large cluster layout.
- Specify more than 120 nodes in your initial Vertica cluster configuration.
- Modify a fault group by adding or removing nodes.

# What is a parallel query?
Parallel query is a method used to increase the execution speed of SQL queries by creating multiple query processes that divide the workload of a SQL statement and executing it in parallel or at the same time.

# What is the Key range partitioning?
where keys are sorted, and a partition owns all the keys from some minimum up to some maximum. Sorting has the advantage that efficient range queries are possible, but there is a risk of hot spots if the application often accesses keys that are close together in the sorted order. In this approach, partitions are typically rebalanced dynamically by splitting the range into two subranges when a partition gets too big.

# What is Hash partitioning?
 where a hash function is applied to each key, and a partition owns a range of hashes. This method destroys the ordering of keys, making range queries inefficient, but may distribute load more evenly. When partitioning by hash, it is common to create a fixed number of partitions in advance, to assign several partitions to each node, and to move entire partitions from one node to another when nodes are added or removed. Dynamic partitioning can also be used.

# What is the Range partitioning?
A table that is partitioned by range is partitioned in such a way that each partition contains rows for which the partitioning expression value lies within a given range. Ranges should be contiguous but not overlapping, and are defined using the VALUES LESS THAN operator.
