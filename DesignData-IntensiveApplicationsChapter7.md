# What is the meaning of ACID?
In databases, ACID refers to the characteristics of the parameters that select the structures of the database management systems. When an action is said to be ACID compliant, it is indicated -to varying degrees- allowing transactions to be carried out.
Atomicity
Consistency
Isolation
Durability

# The most basic level of transaction isolation is read committed. It makes two guarantees: 

1. When reading from the database, you will only see data that has been committed (no dirty reads).
2. When writing to the database, you will only overwrite data that has been committed (no dirty writes). 

#There are a few reasons why it’s useful to prevent dirty reads: 

If a transaction needs to update several objects, a dirty read means that another transaction may see some of the updates but not others. 

If a transaction aborts, any writes it has made need to be rolled back  If the database allows dirty reads, that means a transaction may see data that is later rolled back—i.e., which is never actually committed to the database. Reasoning about the consequences quickly becomes mind-bending.

# What happens if two transactions concurrently try to update the same object in a database?
 We don’t know in which order the writes will happen, but we normally assume that the later write overwrites the earlier write. 

# What is a dirty write?
A Dirty Write occurs when one transaction overwrites a value that has previously been written by another still in-flight transaction.

# How do databases prevent dirty writes?
Most commonly, databases prevent dirty writes by using row-level locks: when a transaction wants to modify a particular object (row or document), it must first acquire a lock on that object. It must then hold that lock until the transaction is committed or aborted. Only one transaction can hold the lock for any given object; if another transaction wants to write to the same object, it must wait until the first transaction is committed or aborted before it can acquire the lock and continue. This locking is done automatically by databases in read committed mode (or stronger isolation levels). 

# What is snapshot isolation
In databases, and transaction processing (transaction management), snapshot isolation is a guarantee that all reads made in a transaction will see a consistent snapshot of the database (in practice it reads the last committed values that existed at the time it started), and the transaction itself will successfully commit only if no updates it has made conflict with any concurrent updates made since that snapshot.
