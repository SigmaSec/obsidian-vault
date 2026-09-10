Two half-adders and an OR gate

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

HalfAdder(a=a[0], 6=6[0] sum = out[0], carry=c1);
FullAdder(a=a[1], 6=6[1], carry=c1, sum=out[1], carry = c2)