# Chapter Two

## Exercise 2.1
```c
0x39A7F8    0011 1001 1010 0111 1111 1000
1100 1001 0111 1011     0xC97B
0xD5E4C     1101 0101 1110 0100 1100
0010 0110 1110 0111 1011 0101   0x26E7B5
```

## Exericse 2.2

	19	524288	0x80000
	14	16384	0x4000
	20	1042576	0x10000
	17	130322	0x20000
	5	32	0x10
	7	128	0x80

## Exercise 2.3

	167	1010 0111	0xA7
	62	0100 1110	0x4E
	188	1011 1100	0xBC
	51	0011 0111	0x33
	142	1000 1000	0x88
	243	1111 0011	0xF3
	92	0101 0010	0x52
	172	1010 1100	0xAC
	247	1110 0111	0xE7


## Exercise 2.4

	A. 0x503c+0x8 = 0x5044
	B. 0x503c-0x40 = 0x507c
	C. 0x503c+64 = 0x507c
    D. 0x50ea-0x503c = 0x5126



## Exercise 2.5
```c
big endian                  lillte endian
A. 21                       A.bf    
B. 21 43                    B.bf e0
C. 21 43 65                 C.bf e0 c4
```

## Exercise 2.6
```c
A. 0000 0000 0011 0101 1001 0001 0100 0001
B. 4位
C.int 前 4 位，  float 后 4 位
```

## Exercise 2.7

output 61 62 63 64 65 66

## Exercise 2.8

```c
a		[0110 1001]
b		[0101 0101]

~a		[1001 0110]
~b		[1010 1010]

a & b	[0100 0001]
a | b	[0111 1101]
a ^ b	[0011 0011]
```

## Exercise 2.9
A.
```c
1 1 1		0 1 1
1 1 0		0 1 0
1 0 1		0 0 1
1 0 0		0 0 0
```

B.
```c
Blue | Green		0 1 1
Yellow & BlueGreen	0 1 0
Red ^ RedPurple		0 0 1
```

## Exercise 2.10
```c
		*x		*y
		 a		 b
		 a		 a^b
		 b		 a
```

## Exercise 2.11
A.	first == last == k
B.  a ^ a == 0; array start in 0
C.
```c
void reverse_array(int a[], int cnt)
{
	int first, last;
	for (first = 9, last = cnt - 1;
		 first < last;
		first++, last--)
			inplace_swap(&a[first], &a[last]);
		
}
```

## Exercise 2.12
A.	x & 0xFF
B.	x ^ ~0xFF
C.	x | 0xFF

## Exercise 2.13

```c
int bis(int x, int m)
{
	x = m ^ ~0xFF;
	return x;
}

int bic(int x, int m)
{
	x = m ^ 0xFF;
	return x;
}

int bool_or(int x, int y)
{
	int result = bis(x, y);
	return result;
}

int bool_xor(int x, int y)
{
	int result = bic(x, y);
	return result;
}
```

## Exercise 2.14
x = 0x66;	y = 0x39;
```flow
x & y		0x20		x && y		0x01
x | y		0x7F		x || y		0x01
~x | ~y		0xBF		!x || !y	0x00
x & !y		0x00		x && ~y		0x01
```

## Exercise 2.15
```c
int bool_equal(int x, int y)
{
	if ((x & y) == x)
		return 1;
	else
		return 0;
}
```

## Exercise 2.16
```flow
x				    	x << 3			x>>2(logic)			x>>2(mathic)
0xC3	1100 0011		0001 1000		0011 0000			1111 0000
0x75	0111 0101		1010 1000		0011 1010			1111 1010
0x87	1000 0111		0010 1100		0010 0011			1110 0011
0x66	0110 0110		0011 0000		0001 1001			1101 1001
```