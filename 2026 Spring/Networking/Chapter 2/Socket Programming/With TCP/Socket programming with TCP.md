Client must contact server
	server must be running 
	must have created socket
Client contacts server by:
	creating TCP sockets, IP addresses, Port number of server
	When client creates socket: client TCP establishes connection to TCP
	When contacted by client, server TCP creates new socket
		Allows server to talk to multiple clients
		Client source port # and IP address used to distinguish clients
