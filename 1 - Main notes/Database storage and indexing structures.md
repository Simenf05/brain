---
aliases:
  - Database structures
  - Database indexing
---

2026-04-28 13:41

Tags: #dbms #database #dsa
# Database storage and indexing structures
The database uses multiple ways of structuring the tables and rows in order to keep the it efficiently searchable and scalable. This includes indexes to search or sort, and also simpler structures for enumeration operations such as joining tables. 
## Internal format 
While we often think about data in databases as rows and tables, internally this notion is not applicable. Inside the database data can be structured in multiple different ways. 
### Records
Often we refer to a row or tuple of data as a record in the database. This is the smallest and simplest storage structure. It contains the attributes of the row in a table, and is normally fixed length. This makes it simple to store, because they can be stored next to each other on the disk. You only need to use an offset to access the elements (like structs in c). With variable length data the storage becomes slightly more complicated. One way to store the record is to start with a header containing pointers to all the elements in the record. ![[Pasted image 20260502113205.png]]
This allows all the records to be variable length. 
### Blocks
A block can be though of as a collection of records. Where each record is identified by a pair of an BlockId and record number within that block. This is often called a Record Identifier (RID). 
#### BlockId and device size
The BlockId often consists of the the device number and index bytes within that block. The index bytes determine the maximum size of the device by the addressable space it enables. With BlockId's at 4 bytes you might use 1 byte for device id and the other 3 bytes for each block on that device. This gives you $2^{24}$ possible blocks within one device! When using 8 bytes for BlockId you can get way larger devices. 




## Structures
### Heapfiles
The 
### Hashfiles
### B+-trees
#### Clustered
#### Unclustered

### LSM trees


## Further reading
- [[Database management system (DBMS)]]