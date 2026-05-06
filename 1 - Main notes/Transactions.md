---
aliases:
  - transactions
---

2026-05-04 14:10

Tags: #database #dbms

# Transactions
A transaction in the context of a database can be thought of as a business logical operation. This can be when buying a train ticket, where it is important that both the money gets spent and that the ticket is delivered. Such a transaction has to always complete both parts of the operation, and it is better to not do any of them then half. Being able to rollback transactions that fail is one of the most important characteristics of transactions in databases. When, and not if, but when a transaction in the database fails, it has to be able to undo the transaction and restore the database. These fails can be in terms of power outages or other errors in the software. More about [[Recovery|recovery]]. 
## Dangers
Some of the dangers relating to concurrency control is *dirty read*, *dirty write*, *unrepeatable read* and *incorrect summary*.
### Dirty read
Dirty read occurs when the a transaction reads data that is not committed. This can happen when transactions 1 starts running and writes a new value to some database object $X$. After this another transaction might try to read $X$ resulting in reading a value that might be rolled back later. 
![[Pasted image 20260504163232.png]]
### Dirty write
Dirty write is when one transaction overwrites another transactions value that is not yet committed. This can happen with a history where two transactions are writing the same value, and the first don't commit before the next also writes. 
![[Pasted image 20260504164431.png]]
### Unrepeatable read / Read skew
This happens when doing operations such as nested joins, that has to read the same object multiple times within a transaction. If another transaction writes while the nested join is running, it causes differing values to be read. ![[Pasted image 20260504172256.png]] 
### Incorrect summary
This happens when the database is performing any aggregate function and the data changes while the aggregate is calculating. The result will be inconsistent. 

## ACID
To prevent dagers relating to transactions and concurrency we use the acronym ACID.
ACID stands for:
- **Atomic:** The transactions in the database either happen or not.
- **Consistency:** The state of the database should be consistent (primary key, checks, etc.) before and after transactions. 
- **Isolation:** Each transaction should not interfere with other transactions while running concurrently. 
- **Durability:** After any transaction commits it should become permanent within the database, even after recovery. 

## Isolation level
![[Pasted image 20260504160416.png]]
The database can configure how much isolation is needed for transactions. In practice no ACID database will use the read uncommitted level. For the other levels they can be used within databases. The further down the levels, the slower the database goes. That is because it has to make sure to not have conflicts. At the lowest level it is serial, and that means transactions run as if they are serial. 
Dangers without for each of the isolation levels:
**Read committed prevents:**
- [[#Dirty read]]
- [[#Dirty write]]
**Repeatable reads prevents:**
- [[#Unrepeatable read / Read skew]]
**Serializable prevents:**
- The phantom problem is that new records might appear while scanning during nested loop joins. 
### Achieving read committed
#### Locking
You can use locks to isolate the different transactions. Each transaction has to get the lock on data objects before reading or writing. These locks can either be mutual exclusive or read only locks. This can be efficient, but is a slightly older way to do it. 
#### Snapshot isolation
More modern solutions use snapshot isolation instead. It is a clean version that keeps older data around until every transaction is finished with the data. This means that the database sacrifices memory for more secure isolation. In some ways this mirrors garbage collection from programming language design. 
### Achieving repeatable read
This is achieved by using [[#Snapshot isolation]].
### Achieving serializable
It means that the transactions perform as if they are serial. It can use two phase locking.
## Transaction conflicts
For two operations to conflict they need to:
1. Belong to different transactions
2. They use the same data element
3. At least one of the operations is a write
Less formally it is when two operations change outcome when they change in order. 
### Serializability

#### Definitions 
**Serial schedule** is a schedule that does not interleave operations from different transactions.
**Serializable schedule** is a schedule that has the same effect on the database as a serial schedule.


## Further reading
- [[Database storage]]
- [[Database management system (DBMS)]]
- [[Database indexing]]
- [[Recovery]]