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

## Exercise 2.17
```flow
	x				B2U4(x)						B2T4(x)
0x0		0000		  0			 				  0
0x5		0101		0*2^3+2^2+0*2^1+2^0=5		-0*2^3+2^2+0*2^1+2^0=5
0x8		1000		1*2^3+0+0+0=8				-1*2^3+0+0+0=-8
0xD		1101		1*2^3+1*2^2+0+1*2^0=13		-1*2^3+1*2^2+0+1*2^0=5
0xF		1111		1*2^3+1*2^2+1*2^1+1*2^0=15  -1*2^3+1*2^2+1*2^1+1*2^0=7
```

## Exercise 2.18
```flow
x		T2U4(x)
-8		8
-3		13
-2		14
-1		15
0		0
5		5
```

## Exercise 2.21
```flow			
									Type			Value
-2147483647-1 == 2147483648U		signed			  1
-2147483647-1 < 2147483647			signed 		  	  1
-2147483647-1U < 2147483647			unsigned 		  0
-2147483647-1 < -2147483647			signed 			  1
-2147483647-1U < -2147483647		unsigned 		  0
```

## Exercise 2.25

```c
float sum_elements(float a[], unsigned length)
{
	int i;
	float result = 0;
	
	for (i = 0; i <= length -1; i++)	// for (i = 0; i < length; i++)
		result += a[i];
	return result;
}
```

## Exercise 2.26
>* A.	when *s size is smaller than *t. strlen(s) - strlen(t) will always bigger than 0
>* B.	Beacuse size_t is unsigned int, always bigger than 0. strlen(s) - strlen(s) will never smaller than 0
>* C.	
```c
int strlonger(char *s, char *t)
{
	return strlen(s) > strlen(t);
}
```

## Exercise 2.27
```c
int uadd_ok(unsigned x, unsigned y)
{
	if ((x+y) < x || (x+y) < y)
		return 0;
	else
		return 1;
}
```

## Exercise 2.28
```flow
		x						-u/4 x
0			0				0			0
5			5				11			B
8			8				8			8
D			13				3			3
F			15				1			1
```

## Exericse 2.29
```flow
	x			y			x+y			x+1/5y				situation
  10100		  10001		  100101       000101					1
  11000		  11000		  110000	   100000					
  10111		  01000		  111111	   11111
  00010		  00101		  000111	   00111
  01100		  00100		  010000	   10000

```

## Exercise 2.30
```c
int tadd_ok(int x, int y)
{
	int sum = x+y;
	int neg_over = x < 0 && y < 0 && sum >= 0;
	int pos_over = x >= 0 && y >= 0 && sum < 0;
	return !neg_over && !pos_over;
}
```