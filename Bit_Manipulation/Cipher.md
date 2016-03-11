#Cipher

## Problem
[Cipher](https://www.hackerrank.com/challenges/cipher)

 * Success Rate: 70.61% 
 * Max Score: 50 
 * Difficulty: Moderate

## Thoughts
There are some tricks in this problem. If we think about it clearly, we can find that the outputs are different between the case K >= N with K < N.

If K >= N, your output must be like:
 `{a[0], a[0] ^ a[1], ... , a[0] ^ a[1] ... ^ a[N], ... }`

And you can find the last N bits is the reverse of the first N bits, so you can store them and print out. 

In this case, the K - N + 1 middle bitsets are always the value of a[0] ^ a[1] ... ^ a[N].


If K < N, it's a little different. The first N - K bits are the same. But the (N - K + 1)th to the Nth bits should remove the bits at the begining. 

As we know that A xor A = 0, so we should just make the result as:
`{a[0], a[0] ^ a[1], ... , a[0] ^ a[1] ... ^ a[K], a[0] ^ a[1] ... ^ a[K + 1] ^a[0], a[0] ^ a[1] ... ^ a[K + 2] ^ (a[0] ^ a[1]), ... }`

So you can find out that you just need to make them xor with the results at the beginning.


Now you can get the whole answer.

You can see the codes at [Cipher](https://github.com/chenyuxiaodhr/hacker\_rank\_solutions/blob/master/Algorithms/Bit_Manipulation/Cipher.cpp).