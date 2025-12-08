2025-12-08 12:07

Tags: #computers #datamaskiner #os #virtualization #vm

# Virtual memory
Virtual memory is one of the responsibilities of the [[Operating System|operating system]], and it provides a layer of separation between each [[process]] running in [[userspace]]. The main motivation for using virtual memory is the abstraction it provides from the hardware, making each and every process think it has access to the entire physical memory on the machine. But in reality the process get a dedicated address-space managed by the [[Operating System|operating system]]. The operating system can isolate and protect every one process from the other processes running at that time. 

## Pages
When describing parts of the virtual memory we use the terminology *page*, and this is similar to the *blocks* used in caches as part of the [[Memory hierarchy|memory hierarchy]]. While *page* and *block* is similar, it is not the same. 
## Translating 
When we have the virtual address can translate it to the physical address. The operating system takes care of that and makes sure we get the correct memory. 
Much like the blocks in caches, the virtual address is made up of the virtual page number and the page offset. The offset corresponds to the address within that page, and the page number is used by the operating system to translate into the correct physical address. 
![[Pasted image 20251208122921.png]]

### Page table
We use a table called the page table to translate from virtual addresses to the physical addresses. Make note that you need a valid bit for all the values in the page table, just like in the caches in the [[Memory hierarchy|memory hierarchy]]. In a way a page table is just a fancy way of caching. 
![[Pasted image 20251208133607.png]]
### Page faults
When the valid bit is off, the physical address is on the secondary storage, meaning the [[Operating System|operating system]] has to take over. The OS moves the value from the secondary storage, and into the main memory, while also adding it to the page table. This is very expensive because the secondary storage is slow. Therefore it is called a page fault, and we want to avoid them at all costs. For this reason the operating system uses complex [[paging algorithms]] in order to minimize the chance of page faults.
## How it works in hardware





### TLB




