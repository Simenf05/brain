2025-12-07 13:10

Tags: #computers #datamaskiner #pipelining #architecture

# Pipelined computer architecture

Pipelining in the computer architecture is a way of increasing throughput of the processor. This is done by allowing the processor work on multiple parts/*stages* of the instructions in parallel. Completing a single instruction may not increase in speed, but when you have a big amount of instructions it will increase drastically. 
## Stages
- Instruction Fetch
- Instruction Decode
- Execute
- Memory
- Write back
## Hazards
There is situations where the pipeline cannot execute two instructions at the same time in the pipeline, these scenarios are called hazards. We have three types of hazards. 
### Structural hazards
Structural hazards happen because the hardware cannot do two instructions at the same time. This is for example if you only have one memory and try to read instruction and read data at the same time. The hardware cannot do both at the same time, and thus a hazard arises. RISC-V is designed with these issues in mind and is therefore not prone to many issues with structural hazards. 

### Data hazards
A data hazard is a hazard that arises when the data needed for a certain instruction is not yet available in the pipeline. For example if you want to do this:
```
sub x1, x2, x3
add x1, x1, x1
```
The load has to finish the entire pipeline to actually load the value into `x1`. Therefore the add instruction cannot start before the load is complete, or we have to implement smarter ways of detecting these problems. 
#### Forwarding
Forwarding is a method of handling data hazards that happen when the first instruction writes a register that the next instruction is using. This cannot handle all combinations of instructions, but works for the example over. The first instruction would 

### Control hazards




