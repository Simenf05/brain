2025-12-01 15:31

Tags: #computers #alu #datamaskiner #floats #floatingpointnumbers

# Floating point numbers
The [[Arithmetic Logic Unit|ALU]] and computer can represent rational numbers without much problem. But how do we represent real numbers? These numbers require infinite precision, which is impossible in a [[finite state machine]].  This calls for compromises and smart design. 

The idea behind the representation of fractional numbers is using scientific notation, and letting the radix point *float*. We use a split notation where the first bit of the number is called the sign bit, as in [[Two's complement|two's complement]]. The rest of the bits are divided into two sections. First is the exponent, and after that is the fraction used in the notation. This is the formula and RISC-V separation of bits:
$$(-1)^\text{S} \times \text{F} \times 2^\text{E}$$
![[Pasted image 20251201160638.png]]





