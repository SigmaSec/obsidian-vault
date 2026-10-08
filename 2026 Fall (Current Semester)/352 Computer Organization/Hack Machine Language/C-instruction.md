16-bits -> cpu -> 16 bits

	ROM
	@17
	D=A
	@3
@4 
	A= 4 at this point
		JMP command will look though the list and jump to the instruction that is in the register
@3
	A = 3
		D = A D =3
		D+; JLT (Jump Less Than)
			means that we will jump to whatever is in the register, as long as it is less than. 
@7
D = A 
@1
D - 1; JGE (Jump Greater Equal)

@7
D = A
@1
M = D
@0
M; JGT(Jump Greater Than)
	D = 0
	0
	7
	7
	7
		A = 0
		7
		7
		1
			M[0..32]= 1
			0,0,0...
			0,0,0,...
			0,0,0...