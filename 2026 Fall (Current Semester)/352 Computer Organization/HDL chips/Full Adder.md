Two half a

Chip:
	CHIP FullAdder {

    IN a, b, c;  // 1-bit inputs

    OUT sum,     // Right bit of a + b + c

        carry;   // Left bit of a + b + c

  

    PARTS:

    HalfAdder(a=a, b=b, sum=h1sum, carry=h1carry);

    HalfAdder(a=h1sum, b=c, sum=sum, carry=h2carry);

    Or(a=h1carry, b=h2carry, out=carry);

}