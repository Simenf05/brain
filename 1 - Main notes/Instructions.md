2025-11-29 12:30

Tags: #datamaskiner #computers #instructions 

# Instructions

## RISC-V instruction fields

### R type instructions
This is the normal register instructions that are on the form `add x1, x2, x3`.
They take in two registers as source and write to one register. 

- Opcode
The opcode (operation code) of the instruction is the basic operation of the instruction. When parsing the other fields this is used to infer what the other fields represents.  
- rd
This is the register destination if the instruction writes to a register. 
- funct3
Additional opcode information.
- rs1
Register source 1.
- rs2
Register source 2.
- funct7
More information for the instruction. 

| funct7 | rs2    | rs1    | funct3 | rd     | opcode |
| ------ | ------ | ------ | ------ | ------ | ------ |
| 7 bits | 5 bits | 5 bits | 3 bits | 5 bits | 7 bits |

### I type instruction
The I type instuctions work the same way as R type, but instead of having two source registers, they have only one and have immediate values. Meaning you can use numeric value to add and do other operations. 
Example:
`addi x1, x2, 30`
`lw x1, 32(x2)`

| immediate | rs1    | funct3 | rd     | opcode |
| --------- | ------ | ------ | ------ | ------ |
| 12 bits   | 5 bits | 3 bits | 5 bits | 7 bits |

### S type instruction 
The last normal type of instruction is the S type, and it is the store instructions. They store to the memory. They give to source registers and a 12 bits of immediate value. 
`sw x1, 120(x2)`

| immediate[11:5] | rs2    | rs1    | funct3 | immediate[0:4] | opcode |
| --------------- | ------ | ------ | ------ | -------------- | ------ |
| 7 bits          | 5 bits | 5 bits | 3 bits | 5 bits         | 7 bits |


