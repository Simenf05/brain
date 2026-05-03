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
Hashfiles typically have 80% fill. And therefore this needs to be accounted for when doing scans of hashfiles. 
![[Pasted image 20260503093949.png]] 

### B+-trees
The most common type of index is the B+-tree. This type of index is made for keeping sorted data fast and searchable. It works by having keys that point to the next level in the tree. For a key on a $\text{level}>0$ the left pointer for each value will point to keys that are strictly smaller, and keys on the right pointer will be equal or larger. At $\text{level} = 0$ all the keys are stored, and if the tree is in the clustered variant the records are also stored there. 
The fill degree of the B+-tree is generally regarded as $2/3$, meaning that at all times only two thirds of the space is used. 
##### Clustered
For clustered B+-trees you keep the records stored at $\text{level} = 0$ in the tree. This makes them efficient for range selects and sorts. But the tradeoff is that they use more space. Therefore you need to use more blocks to store less keys. 
##### Unclustered
With unclustered B+-trees you use a separate structure to store the records, and only keep the keys in the B+-tree. This can be done with a [[Database storage#Database storage#Heapfiles|heapfile]]. This makes these trees bad for scans, because you always have to read one more block for each lookup, and for a scan that adds up. The benefit of the unclustered variant is that they take up less space, and can contain far more keys on less blocks. On the lowest level they only have to keep the key and the [[Database storage#BlockId and device size|BlockId]]. 
### Log-Structured Merge trees (LSM trees)
LSM trees is a database structure made for fast writes. While B+-trees are better for reads, the LSM trees are best at writing much data. It uses three main components memtable, SST file and logfile. 
#### Memtable, SST file and logfile
The memtable is the most recently written data, and it is stored in the main memory. This makes it fast to read from. When the memtable is full, it is made into a SST file. This is a file composed of the same data from the memtable, but we use a hierarchy for managing the data. When records are stale, and not read often the sink in the structure. This allows the most relevant data to be at the top. Logfiles are used to keep track of the data. More about that in logging section. It uses write-ahead logging (WAL).
![[Pasted image 20260503131624.png]]

## Further reading
- [[Database storage]]
- [[Database management system (DBMS)]]