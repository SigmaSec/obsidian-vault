Client: DHCP Discover
	SRC: 0.0.0.0, 68
	dest:255.255.255.67
	yiaddr: 0.0.0.0
	Transaction ID: 654
Server: DHCP Offer
	Broadcast: I'm a DHCP server, here is your IP address you can use
	EX:
		Src: 223.1.2.5, 67
		dest: 255.255.255.255, 68
		yiaddrr: 223.1.2.4
		Transaction ID: 654
		lifetime: 3600 secs
These two steps can be skipped if a client is not new. If a client remembers its connection and wishes to reuse a an IP DHCP will allow it.
Client: DHCP req
	src: 0.0.0.0, 68
	dest: 255.255.255.255, 67
	yiaddrr: 223.1.2.4
	transaction ID: 655
	lifetime: 3600 sec
Server: DHCP ACK:
	src: 223.1.2.5, 67
	dest: 255.255.255.255, 68
	yiaddrr: 223.1.2.4
	transaction ID: 655
	lifetime: 3600 sec