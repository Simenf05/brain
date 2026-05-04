---
aliases:
  - transactions
---

2026-05-04 14:10

Tags: #database #dbms

# Transactions (Databases)
A transaction in the context of a database can be thought of as a business logical operation. This can be when buying a train ticket, where it is important that both the money gets spent and that the ticket is delivered. Such a transaction has to always complete both parts of the operation, and it is better to not do any of them then half. Being able to rollback transactions that fail is one of the most important characteristics of transactions in databases. When, and not if, but when a transaction in the database fails, it has to be able to undo the transaction and restore the database. These fails can be in terms of power outages or other errors in the software. More about [[Recovery (Databases)|recovery]]. 
## Dangers
Some of the dangers relating to concurrency control is *dirty read*, *dirty write*, *unrepeatable read* and *incorrect summary*.
### Dirty read
#### What 
#### When
### Dirty write
#### What 
#### When
### Unrepeatable read
#### When
### Incorrect summary
#### When
## ACID
To prevent dagers relating to transactions and concurrency we use the acronym ACID.
ACID stands for:
- **Atomic:** The transactions in the database either happen or not.
- **Consistency:** The state of the database should be consistent (primary key, checks, etc.) before and after transactions. 
- **Isolation:** Each transaction should not interfere with other transactions while running concurrently. 
- **Durability:** After any transaction commits it should become permanent within the database, even after recovery. 

## Isolation level
![[Pasted image 20260504160416.png]]





## Further reading
- [[Database storage]]
- [[Database management system (DBMS)]]
- [[Database indexing]]