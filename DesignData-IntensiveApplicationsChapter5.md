# What "Replication" means and what are some reasons to replicate data?
- Means keeping a copy of the same data on multiple machines that are connected via a network.

- To keep data geographically close to your users (and thus reduce latency)
- To allow the system to continue working even if some of its parts have failed
(and thus increase availability)
- To scale out the number of machines that can serve read queries (and thus
increase read throughput)

# How the Master-slave replication works?
- Master-slave replication enables data from one database server (the master) to be replicated to one or more other database servers (the slaves). The master logs the updates, which then ripple through to the slaves. The slave outputs a message stating that it has received the update successfully, thus allowing the sending of subsequent updates. Master-slave replication can be either synchronous or asynchronous. The difference is simply the timing of propagation of changes. If the changes are made to the master and slave at the same time, it is synchronous. If changes are queued up and written later, it is asynchronous.

#What is the principal differences between Synchronous and Asynchronous Replication?
- The primary difference between synchronous replication and asynchronous replication is the way in which data is written to the replica. Most synchronous replication products write data to primary storage and the replica simultaneously. As such, the primary copy and the replica should always remain synchronized. In contrast, asynchronous replication products copy the data to the replica after the data is already written to the primary storage. Although the replication process may occur in near-real-time, it is more common for replication to occur on a scheduled basis. For instance, write operations may be transmitted to the replica in batches on a periodic basis (for example, every one minute). In case of a fail-over event, some data loss may occur.

# An automatic failover process usually consists of the following steps:
1 - Determining that the leader has failed. There are many things that could poten‐
tially go wrong: crashes, power outages, network issues, and more. There is no
foolproof way of detecting what has gone wrong, so most systems simply use a
timeout: nodes frequently bounce messages back and forth between each other,
and if a node doesn’t respond for some period of time—say, 30 seconds—it is
assumed to be dead. (If the leader is deliberately taken down for planned mainte‐
nance, this doesn’t apply.)

2 - Choosing a new leader. This could be done through an election process (where
the leader is chosen by a majority of the remaining replicas), or a new leader
could be appointed by a previously elected controller node. The best candidate for
leadership is usually the replica with the most up-to-date data changes from the
old leader (to minimize any data loss). 

3 - Reconfiguring the system to use the new leader. Clients now need to send
their write requests to the new leader (we discuss this in “Request Routing” on
page 214). If the old leader comes back, it might still believe that it is the leader,
not realizing that the other replicas have forced it to step down. The system
needs to ensure that the old leader becomes a follower and recognizes the new
leader.

# How a Statement-based replication can be broken?
- Any statement that calls a nondeterministic function, such as NOW() to get the
current date and time or RAND() to get a random number, is likely to generate a
different value on each replica.

- If statements use an autoincrementing column, or if they depend on the existing
data in the database (e.g., UPDATE … WHERE <some condition>), they must be
executed in exactly the same order on each replica, or else they may have a differ‐
ent effect. This can be limiting when there are multiple concurrently executing
transactions.

- Statements that have side effects (e.g., triggers, stored procedures, user-defined
functions) may result in different side effects occurring on each replica, unless
the side effects are absolutely deterministic.

# What is logical log replication?
- Logical replication is a method of replicating data objects and their changes, based upon their replication identity (usually a primary key). We use the term logical in contrast to physical replication, which uses exact block addresses and byte-by-byte replication. PostgreSQL supports both mechanisms concurrently. Logical replication allows fine-grained control over both data replication and security.

# What is Trigger-based replication?
- To implement trigger-based replication, use event triggers stored in the database. When an event to be replicated occurs (that is, a record is created, modified, or deleted) the database uses the event to record the change in a replication change log. ABL (Advanced Business Language) provides full support for trigger-based replication.
