A method to show negative binary number, inverting the bits of the positive number
If Most Significant Bit (leftmost bit) is 1, binary represents negative number
	011 -> 3 
	000 -> +0
	100 -> -3
	111 -> -0
If first bit is 0, number is positive
If first bit is 1, number is negative
	001 -> 1 in decimal
	010 -> 2 in decimals
	011 -> expected decimal is 3
		0000 0101 -> +5
		1111 1010 -> -5
		1111 1111 -> -0
		
		0000 0111 -> +7
		1111 1010 -> -5
		0000 0010 -> 2
In one complements all 1's means 0
all 0's mean 1
