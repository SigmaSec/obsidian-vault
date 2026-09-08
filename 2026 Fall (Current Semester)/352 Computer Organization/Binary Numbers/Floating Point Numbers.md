We use this to represent decimals.
	example: 631.25 = 6.3125 * 10^2 

This is the key insight needed to understand floating point numbers, we need three things: a fixed point number (called the _significand_ or the _mantissa_), an exponent, and a sign bit (0 for positive and 1 for negative numbers). While there are many ways this could be done, the industry standard is the IEEE 754.
![[Pasted image 20260908131554.png]]

are two further concepts needed to fully explain the IEEE 754 standard: the leading bit convention, and the exponent bias, but we will not concern ourselves with these in this course.

Question 13:
	What would be an advantage of using a floating-point number over a fixed point number?
		Being able to display or represent a number that is not a whole number. If we were not able to show decimals, we would not be able to do online banking.
