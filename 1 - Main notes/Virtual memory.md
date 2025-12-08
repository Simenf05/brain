2025-12-08 12:07

Tags: #computers #datamaskiner #os #virtualization #vm

# Virtual memory
Virtual memory is one of the responsibilities of the [[Operating System|operating system]], and it provides a layer of separation between each [[process]] running in [[userspace]]. The main motivation for using virtual memory is the abstraction it provides from the hardware, making each and every process think it has access to the entire physical memory on the machine. But in reality the process get a dedicated address-space managed by the [[Operating System|operating system]]. The operating system can isolate and protect every one process from the other processes running at that time. 

## Pages
When describing parts of the virtual memory we use the terminology *page*, and this is similar to the *blocks* used in caches as part of the [[Memory hierarchy|memory hierarchy]]. While *page* and *block* is similar, it is not the same. 

![[Pasted image 20251208122921.png]]
## How it works in hardware


### TLB




