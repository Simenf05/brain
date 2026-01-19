---
aliases:
---

2026-01-19 12:43

Tags: #os 

# Thread
Threads work the same way as a [[Process]] but they share the same address space. Therefore it makes it easy to share memory within a bigger process. 

### Threads share
- Process ID (PID)
- [[Address space]]
- [[File descriptors]]
- Current working directory
- Other resources
### Threads don't share
- Thread ID (TID)
- Set of registers, including program counter and stack pointer
- Stack for local variables and return addresses

## Further reading
- [[Process]]
