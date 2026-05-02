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

## Further reading
- [[Database structures]]