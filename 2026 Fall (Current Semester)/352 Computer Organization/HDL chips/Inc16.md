Two inbuilt constant buses, 'true' and 'false' that can be used for inputs to chips. constant values of 1 and 0 
indexing buses can use '..' symbol as slice operator in first 8 bits
Chip input buses can be indexed, and16[0...7]=true,a[8..15]=false, b=b, out=out); is valid where input bus 'a' split to take all once for the first 8 bits and all 0s for the last 8 bis