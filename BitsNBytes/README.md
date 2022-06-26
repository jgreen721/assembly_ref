# Bits n Bytes, and how they lead to Hex

## Bits

1 bit = 0 or 1;
2 bit = (2 ** 2) = 4 possible expressions
3 bit =(2 ** 3) = 8
4 bit = 16..

n bit = 2 \*\* N nums

---

## Byte

8bits = 1 Byte

1 Byte Represent 256 possible manners ( -- which leads into ascii conversions)

`Example(1Byte): 11111111, 00000010, 11001010 `

`Convert: 10011101 --- (128,64,32,16,8,4,2,1)`

### = 2 ** 7 + 2 ** 4 + 2 ** 3 + 2 ** 2 + 2 \*\* 0;

### = 128 + 16 + 8 + 4 + 1

### = 157

## Hexadecimal

## 0...9,A,B,C,D,E,F

### 10,11,12,13,14,15

`0x3EA = (3 * 16 ** 2) + (14 * 16 ** 1) + (10 * 16 ** 0)`

-- the power of(\*\*) is derived from position, again:

`1002`

(16^2 _ 3) 760
(16^1 _ 14) = 16 _ 14 = 224
(16^0 _ 10) = 10 \* 1 = 10
`760 + 224 + 10 = 1002`

`0xBEEF = (11 * 16 ** 3) + (14 * 16 ** 2) + (14 * 16) + (15)`

#Bitwise Operators

### Operations performed on bits

& = And <br/>
| = Or<br/>
~ = Not<br/>
<< = Left Shift<br/>
'>>' == Right Shift<br/>
^ = XOR

# & Operator

## (Both bits agree to carry; x=1,y=1,z=1, x=1,y=0,z=0,x=0,y=1,z=0)

7 = 0111 <br/>
& <br/>
4 = 0100 <br/>

---

     0100     4 & 7 = 4

# | Operator

## (x=1,y=1,z=1/x=1,y=0,z=1/x=0,y=1,z=1)

7 = 0111 <br/>
| <br/>
4 = 0100 <br/>

---

     0111   4 | 7 = 7

# ~ Operator

## (Not is unary; only requires 1 bit)

~5 = -6
~-6 = 5

~ -n = n-1
~ n = -n-1

On bits, it seems?? to give the inverse, or compliment so
~01011 - > 10100

& - bitwise AND operator
&& logical AND operator <- the one Im used to using (logical || as well)

`x=1,y=2` (x= 00000001, y = 00000010)

`if(x&y)` 00000001 & 00000010 = 00000000 = 0 (wont fire condition)<br/>
`print("You have a value > 0")` <br/>
`if(x&&y)` if x(00000001), if y(00000010) (both are > 0,)
TRUE && TRUE = TRUE = 1 <br/>
`print("the second condition fired, you have a value > 0.")` <br/>
