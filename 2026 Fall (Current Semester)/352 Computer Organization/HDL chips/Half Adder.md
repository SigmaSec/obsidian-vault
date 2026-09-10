Half adder is a chip that adds two bits. Two outputs, the "sum" and "carry" bit
	XOR can be sum and carry can be AND gate (?)
XOR is good for representing additions if the carry bit is not needed, but which gate would be good for the carry bit?
	And gate

Half-Adder chip: 
	CHIP HalfAdder {
	IN a, b;    // 1-bit inputs
	OUT sum,    // Right bit of a + b
	carry;  // Left bit of a + b
	PARTS:
	Xor(a=a, b=b, out=sum);
	And(a=a, b=b, out=carry);
}
