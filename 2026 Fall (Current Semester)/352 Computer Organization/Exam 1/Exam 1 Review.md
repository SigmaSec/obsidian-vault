@5 
D=A
@6
M=D
A?

What will be in a and what will be in d?
@5 - put 5 into A
D=A - put 5 into D 
@15 - 15 in A 
0;JMP - would jump to line 15

A = 15
D = 5

@3 - Set A to 3
D=A - Set D to A (3)
@5 - Set A to 5
M=D - Set M at 5 to D (3)
D=A - Set D to A (5)
@3 - Set A to 3
M=D - Set M at 3 to D (5) (M[3] = 5, M[5] = 3)

@1 - Set A to 1 
D=A - Set D to A (D=1) 
@2 - Set A to 2
M=D + 1 - Set M[2] = D (M[2] = 2)
M; JEQ (Jump Equivalent) -  We do not jump because M is not equal to 1 
D-1; JEQ - Compares D at current position (currently 1) - 1= 0, so we jump. We jump to whatever is in A (currently 2) 

2's compliment
review this 
Flip the bits 
then add both the flipped and the original together
then you will get zero 

how to get -5 
0101
1010
1011

X -> multiplxor
y -> multiplxor 
sel -> 1 
sel -> y

a -> multiplxor
b -> multiplxor
c ->multiplxor
d -> multiplxor
sel -> 00 01 10 11
sel output -> 0011

in -> demultiplexor
sel -> 10
demultiplexor -> 0 0 in 0 

DFF: output(t) = in (t-1) 
CLK in out
	0 1 ?
	1 1 1
	2 0 1
	3 0 0
	4 _ 0
out(t) = out(t-1)
DFF out -> back into the DFF for the previous time step