2025-12-01 15:31

Tags: #computers #alu #datamaskiner #floats #floatingpointnumbers

# Floating point numbers
The [[Arithmetic Logic Unit|ALU]] and computer can represent rational numbers without much problem. But how do we represent real numbers? These numbers require infinite precision, which is impossible in a [[finite state machine]].  This calls for compromises and smart design. 

The idea behind the representation of fractional numbers is using scientific notation, and letting the radix point *float*. We use a split notation where the first bit of the number is called the sign bit, as in [[Two's complement|two's complement]]. The rest of the bits are divided into two sections. First is the exponent, and after that is the fraction used in the notation.
RISC-V separation of bits:
![[Pasted image 20251201160638.png]]
This is the general formula for calculating the value of the float. 
$$(-1)^\text{S} \times \text{F} \times 2^\text{E}$$
Although this formula is nice many use a slightly more sophisticated version. RISC-V uses this formula instead, and the point is that we add a extra one in front of the fraction part. The reason for this is that we get one extra bit, and that makes it possible to represent more numbers. The only number that does not have this bit is zero, and therefore full zero is equal to zero. The rest follow this formula:

$$(-1)^\text{S} \times (1+\text{F}) \times 2^\text{E}$$
This is the IEEE 754 standard of floating point numbers, and they are widely used on many different computer. Using a formula like this we can represent many large numbers, but with $2^\text{E}$ the smallest number we get is $2^0 = 1$. That is why we need to have a bias, making the exponent be small and large. 
$$(-1)^\text{S} \times (1+\text{F}) \times 2^{\text{E}-\text{Bias}}$$
![[Pasted image 20251204092243.png]]
This can represent:
$$\pm1.00000000000000000000000_\text{two}\times2^{-126}$$
to:
$$\pm1.11111111111111111111111_\text{two}\times2^{127}$$





