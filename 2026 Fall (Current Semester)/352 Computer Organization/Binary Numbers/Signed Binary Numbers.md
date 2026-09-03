How do we represent a negative number in binary? 
	If you had a specific bit that would indicate positive/negative, it would not preserve the addition
We have to use 2's compliment.
	a + (-a) = 0 or a + (-a) = 2^n, which is basically conserving the 0.

What is the 4 bit representation of:
	A.) -1
		1111
	B.) -8
		1001
	C.) -4
		0100 -> convert to 1011 -> add one -> 1100
	D.) -2
		0010 and 1101 which equals 1111, so then add 1 to it, 1110

Take bit inversion (change the values at each position) and then add a one (1) 

![[Pasted image 20260903131720.png]]

How to convert from 2's complement to decimal? 
	