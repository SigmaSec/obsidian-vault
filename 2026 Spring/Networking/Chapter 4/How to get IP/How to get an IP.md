Q?: how does network get subnet part of IP address
	A: gets allocated portion of its provider ISP's address space
		ISP's block: 11001000 000101111 00010000 000000000 200.23.16.0/20
			200.23.10.0 -> 200.23.255.255 <- available hosts portions are indicated by 255
		Subnet 0 -> 200.23.? (must be >= 16) .? (0-255)
			200.23.16.0/23
		Subnet 1 -> 
			200.23.18.0/23
		Subnet 2
			200.23.20.0/23
		....
		Subnet 7
			200.23.30.0/23
				all use Fly-by-night-ISP -> "send me anything beginning with 200.23.16.0/20" -> internet
Hexa:
	0 -> 000
	1 -> 001
	2 -> 010
	3 -> 011
	4 -> 100
	5 -> 101
	6 -> 110
	7 -> 111
11001000.000101111.00010000.000000000
1100100.00010111.0001 is Network portion
1100100.00010111.0001000 is subnet portion. Can Identify using the last 3 bits
1100100.00010111.0001001 is subnet 