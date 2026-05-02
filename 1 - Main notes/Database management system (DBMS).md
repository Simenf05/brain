---
aliases:
  - DBMS
  - dbms
---

2026-04-28 13:40

Tags: #dbms #database

# Database management system (DBMS)
Database management systems are composed of several components that work together in order to securely and reliably store information. Such components include, but not limited to, SQL compiler, optimizer, executor, database buffer, log and SQL catalog. 
## SQL compiler
The SQL compilers responsibility is to use the SQL you provide and turn it into the [[Relational algebra|relational algebra]] that is used internally in the database. The **SQL catalog** is used as a reference book for the translation. 
## Optimizer
When the database has the internal [[Relational algebra|relational algebra]] representation of the query the query is to then to optimize the query to the best potential. This is done with statistics of the entire database that can help infer the best strategies for queries. 
The crucial part about the optimizer is that it cannot change the result of the query, only the execution. In technical terms this means that the queries has to be equivalent, and for two queries to be equivalent they have to give the same output for every possible database. For the optimizer it should try to find the optimal [[Relational algebra|relational algebra]] for the current database, that is still **equivalent** to the original query. 
## DB buffer
The database buffer is the part of the database that stores the most important information. Usually writing to the disk is slow, and therefore we mostly write to the buffer and then occasionally the buffer is written to the disk. The more important parts (like the [[Database logging|log]]) is written more frequently while the data rarely is written. 

## Storage and indexing
One of the most important parts of the database is how the database structures the data stored. This is done through multiple types of data structures within the storage. More about them [[Database storage and indexing structures|here]].

## Further reading
- [[Database storage and indexing structures]]
- [[Relational algebra]]
- [[Database logging]]