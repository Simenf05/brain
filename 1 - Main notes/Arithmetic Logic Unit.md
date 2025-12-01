2025-11-29 17:11

Tags: #computers #datamaskiner #alu #arithmeticlogicunit #arithmetic #cpu

# Arithmetic Logic Unit

The arithmetic logic unit is the part of the processor that performs the most basic computational operations. These operations consist of:
- addition
- subtraction
- multiplication
- division
The arithmetic logic unit has to support both real numbers and fractional numbers, but how do we represent that in hardware? 

## Addition
Addition is simple, and works just the same way it does in elementary school. You start with both the least significant bits, and sum them together. If the value is 1, then the result is 1. If the value is 2 or 3, then the value carries over to the next digit. This way we get:

![[Pasted image 20251201104401.png]]

This can be implemented with logic gates in a simple way, we need an AND gate to check if the bit is carrying over. And then we need an OR gate to check for the result bit value. It is simple to see how this can be represented only by logic gates. 
### Overflow
There is one issue with this approach, and that is overflow. What if the final bits are suppose to carry over? Where would they carry over to? The answer is that there is no definite answer, and computer designers and programmers handle it differently. In some programming languages, like c and java, it is just ignored. 

## Subtraction
How do we subtract numbers? The simple solution is to use the [[two's complement]], and convert the number from a positive number to a negative number. When the number is negative, you use the normal addition method to calculate the result. 
![[Pasted image 20251201110404.png]]
This turns into this:
![[Pasted image 20251201110422.png]]

This is one of the motivations for using [[two's complement]], and we can save space and time by keeping operations like this simple. 

## Multiplication
Multiplication and division is where it gets more tricky. To multiply we use this circuit.
![[Pasted image 20251201123704.png]]

It works similar to a for loop. For each turn you take the least significant bit of multiplier and multiply it with the multiplicand register. 
Giving you either:
$$(0\times\text{Multiplicand})$$
or:
$$(1\times\text{Multiplicand})$$
To compute this you conditionally add the $\text{Multiplicand}$ to the $Product$ register. 
This looks like this:
$$\text{Product}_{new}=\text{Product}_{old} + (\text{Multiplier}_{0} \times \text{Multiplicand})$$
Where $\text{Multiplier}_{0}$ signifies the least significant bit of the multiplier register. 
When this is done the $\text{Multiplicand}$ is shifted left once and the $\text{Multiplier}$ is shifted right. This sets up the next part of the multiplication. 

To refine the model even more, and use less space we can use the product to also hold the multiplier. The product also holds one extra bit as the carry-out of the adder. 
![[Pasted image 20251201123919.png]]

### Faster multiplication
To increase the speed of the multiplication, we can unroll the 32-bit adder. Instead of having one adder we have 31 of them. This way we can do the add in parallel and therefore speed the the multiplication up, but sacrificing space.   

