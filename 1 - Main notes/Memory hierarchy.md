---
aliases:
  - memory hierarchy
---

2025-12-07 18:07

Tags: #computers #datamaskiner #memory

# Memory hierarchy
The memory in a computer uses a structure much like a pyramid, this is called the memory hierarchy. The priciple is that we have both fast and small memory and slow and big memory. For each size and speed we have different layers, and we walk through these layers in an attempt to find the address we are looking for. 
## SRAM
This is the fastest type of memory, and it is located within the [[CPU]]. This makes it the fastest while also being the smallest. The name SRAM comes from static RAM, and this is because it, unlike DRAM, persists. SRAM is made up with a bunch of latches and is therefore very fast, but the size has to be small if it is to be fast.
## DRAM
DRAM is dynamic ram, and it is called dynamic because it has to update the values itself to persist them. DRAM is cheaper in size, but also slower. DRAM is used in the outer parts of the CPU. 

We also have Flash memory and Disk memory.

# Caches
## Direct mapping
Direct mapping is the most straight forward structure of cache. It normally uses just the modulo of the amount of blocks to determine the address within the cache. This way every address maps to exactly one address in the cache. We get the simple formula:
$$(\text{Block address})\mod{(\text{Blocks in cache})}$$
If the amount of blocks is a power of 2, then the block address can be computed just by using the $log_2(\text{Blocks in cache})$ least significant bits of the normal address. 
![[Pasted image 20251207200728.png]]

To know if the location we are looking up actually is storing the desired value, and not some other value that could have the same modulo we use tags. A tag is a value we store in order to know if the word stored in the cache is the correct value. In a directly mapped cache the tag is just the rest of the memory address. 
We also need one more thing, and that is a bit to mark if the bit is valid or not. The valid bit is just there to prevent unused cache blocks to be able to match actual memory addresses. When a value is written to the cache it will set the valid to 1, and from then on the block will be valid, even when changed. But if you restart the computer, then all blocks start out not valid. 
When looking up in the cache the least significant bits will be used to find the correct block in the cache. After finding the correct block you need to look at the valid bit, and then if the block is valid you can compare the address to the tag. If they match then you have a cache hit. 

Since words are aligned to 32 bits at a time, the two first bits of the address can be ignored because they would align to the bytes within a word. 
This gives us this structure:
![[Pasted image 20251207213320.png]]

- Cache size is $2^n$ blocks, so $n$ bits are used for the index
- Block size is $2^m$ words, so $m$ bits are used for the word within the block (word offset)
- Two bits are for the byte part of the address (byte offset)
Size of tag is therefore with a 32 bits address:
$$\text{Tag bits} = 32-(n+m+2)$$
Total number of bits in directly mapped cache:
$$\text{Total number of bits} = 2^n\times(\text{block size}+\text{tag size}+\text{valid field size})$$
## Set-associative mapping
With set-associative mapping we allow each index to map to multiple blocks at the same time. Each set will contain $n$ blocks, and is then a $n$-way set-associative mapping. One way to view this is that direct mapping is a 1-way set-associative mapping, and an extreme of this spectrum. The other extreme is a fully-associative mapping, where there is just one set with all the blocks in it. 
When looking up values in a set-associative mapping, we have to search every value for the one with the correct tag. This makes fully mapped structure hard for large systems because the searching would be to expensive. 
![[Pasted image 20251208113712.png]]

This is the formula for the index using set-associative mapping:
$$(\text{Block number})\mod{(\text{Number of sets in the cache})}$$



