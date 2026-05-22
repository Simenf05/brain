---
aliases:
---

2026-05-22 11:52

Tags: #os #virtualization #

# Virtualizing the CPU
One of the fundamental motivations for having [[Operating System]]s is to allow software to virtualize the hardware running beneath. Part of that includes providing a virtual layer of the [[Central Processing Unit|CPU]], that [[Process|processes]] can run on. One of the desirable uses for this abstraction is that we want each process running on the computer to act as if it has the entire CPU to itself. The motivation for this is that it makes it easier to make programs for the user. 
## Time sharing
To implement the abstract process, that has the entire CPU to itself, we use the concept of time sharing. Time sharing is when you have one central program (i.e. the operating system) that controls when all the other programs run. This way the computer can run multiple programs at once. But how is it achieved?
## Isolating programs
The way we achieve 
## Getting the control back
One of the problems is how the operating system can get back the execution from running processes. 
### Timers

## Further reading
- [[Operating System]]
- [[Central Processing Unit]]
- [[Process]]
- [Time sharing at MIT](https://www.youtube.com/watch?v=Q07PhW5sCEk)