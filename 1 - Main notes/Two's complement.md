2025-11-27 17:58

Tags: #computers #datamaskiner

# Two's complement

The two's complement is representation of numbers, used in computers. It suggests that we should use the first bit of the 32-bit word as the sign bit. The sign bit is the most significant bit of the number, and has index 31. This bit determines if it is a positive number or negative number. The structure looks a lot like this

| sign bit \[31] | \[30-24]   | \[23-16]   | \[15-8]    | \[7-0]     | base 10 |
| -------------- | ---------- | ---------- | ---------- | ---------- | ------- |
| `0`            | `0000000`  | `00000000` | `00000000` | `00000000` | 0       |
| `0`            | `0000000`  | `00000000` | `00000000` | `00000001` | 1       |
| `0`            | `0000000`  | `00000000` | `00000000` | `00000010` | 2       |
| `0`            | `11111111` | `11111111` | `11111111` | `11111111` | max     |
| `1`            | `0000000`  | `00000000` | `00000000` | `00000000` | -min    |
| `1`            | `11111111` | `11111111` | `11111111` | `11111101` | -3      |
| `1`            | `11111111` | `11111111` | `11111111` | `11111110` | -2      |
| `1`            | `11111111` | `11111111` | `11111111` | `11111111` | -1      |

This allows a word to represent both negative numbers and positive numbers. But why not just shift all the values to be in the middle and have `00000000 00000000 00000000 00000000` be the smallest negative number, and `11111111 11111111 11111111 11111111` be the largest positive number. The reason is that two's complement is very useful when doing arithmetic operations on the numbers, is that it allows you to convert positive numbers to negative numbers and therefore replace subtraction with addition. 
### Converting positive numbers to negative numbers
To convert a number you flip all the bits and then add one. 

| `11111111` | `11111111` | `11111111` | `11111001`     | `-7` |
| ---------- | ---------- | ---------- | -------------- | ---- |
| `00000000` | `00000000` | `00000000` | `00000110 + 1` | `7`  |

| `00000000` | `00000000` | `00000000` | `00000111` | `7`  |
| ---------- | ---------- | ---------- | ---------- | ---- |
| `11111111` | `11111111` | `11111111` | `11111000 + 1` | `-7` |

