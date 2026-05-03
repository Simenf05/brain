---
aliases:
  - index
---

2026-05-03 08:42

Tags: #dbms #database

# Database indexing
In the database it is important to be able to find and look up information fast. To do this we use indexes. Index is a general term for a data structure that can be used to retrieve information fast. When using primary keys in the database, you need an index to make sure that new inserted elements are unique. 
### Hashfiles
Hashfiles exists in two versions. The first is the static hashing. With this method you have to decide on the size of the hash beforehand, which can be hard for a growing database. We also have extensible hashing, which grows with the database. 
#### Static hashing
When using static hashing you have a constant number of blocks. This means that the blocks can and will get filled up. The most basic hashing function is just using the modulo of the key on the number of blocks.
$$h(K) = K\mod{N}$$
To cope with the blocks getting filled up we use a few different strategies. 
##### Internal addressing
With internal addressing you allow the record to be placed in the next available block in the hash. As might be obvious, the hash can still become full. And when that happens the hash stops working. 
##### External addressing
With external hashing you allow the filled blocks to link to other block with linked lists. This allows the hash to grow indefinitely, with the cost of searching. If the linked lists grow large you will need to search many blocks, and that makes the hashing useless. 
##### Multiple hashing
With this strategy you use another hash function to store the record. This might also be referred to as distributed hashing.  
![[Pasted image 20260503092120.png]]
#### Extensible hashing
To improve on the problems with static hashing we use **extensible hashing**. It works by allowing the amount of slots in the hash to increase. This is done by keeping the slots and information separate. We also have a notion of local and global depth, this determines how many bits to use when looking up the values. 
##### Directory doubling
This happens when the hash function hashes and finds that the slot is full and the local and global depth is equal. When the slot it full it has to double the directory and add a new slot. This is done by increasing the global and local depth by one and copying the current slot. After the copy it has to rehash all the values and use the new slots. 
![[Pasted image 20260503093949.png]] 

### B+-trees
The most common type of index is the B+-tree. This type of index is made for keeping sorted data fast and searchable. It works by having keys that point to the next level in the tree, and 
#### Clustered
#### Unclustered

### LSM trees
## Further reading
- [[Database storage]]
- [[Database management system (DBMS)]]