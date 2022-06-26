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

`& = And
| = Or
~ = Not
<< = Left Shift

> > == Right Shift
> > ^ = XOR`