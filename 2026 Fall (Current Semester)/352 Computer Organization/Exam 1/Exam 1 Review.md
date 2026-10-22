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
M=D - Set M to D (3)
D=A - Set D to A (5)
@3 - Set A to 3
M=D - Set M(5) to D (5)

A?
D?
M[3]? 
M[5]?