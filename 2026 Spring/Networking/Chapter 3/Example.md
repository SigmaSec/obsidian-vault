Control packet size = C bits
Object size = O Bits
Link's Rate = R bps
Link's Rate is small -> d(prop) ~= 0
(Client -> Server) 
Control packet to request connection = C/R
(Server -> Client) 
Control packet to accept connection request = C/R
Control packet
Test = C/R + C/R + d(propagation) = 2 C/R
T(base) = test + C/R + O/R = 2 C/R + C/R + C/R = 3C/R + C/R
T(objects) = (3C/R + O/R) + (3C/(R/6) + O/(R/6) + (3C/(R/3))+ O/(R/3)) 
	Because we are sending in parallel, entire bandwidth is divided by 6.


T(objects) = (3C/R + O/R) + 9x(3C/R + O/R) <- Non-persistent without parallel