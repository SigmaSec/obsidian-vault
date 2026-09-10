Servers that a target may have
	OSINT -> network topology of target (Radford Example)
		DNS
		Mail
		NTP
		Internal (onecampus)
		rucs
		Banner

Question 1: 
	Nmap is a tool for scanning and/or enumeration 

DMBS -> frontend (web browser) 
	This could be a misconfigured SQL database that has a vulnerability

Question 2: 
	How many ways of recon? 
		2, passive and active

Question 3:
	Which of the following are passive scanners:
		Wireshark and p0f

Question 4:
	What type of scan will a pen-tester use if they do not wanted to be seen?
		Passive

Question 5:
	ICMP scans are typically blocked by firewalls (T/F?)
		T

Question 6:
	Port typical for web servers:
		80

Question 7:
	HTTP uses which of the following as its transport protocol:
		TCP

Question 8:
	3 way handshake:
		SYN -> SYN +ACK -> ACK

Question 9:
	

How 

Nmap -> client which sends question to server
	server responds collects response -> this is now called a fingerprint
		fingerprint -> pro ftpd 1.3.5

client | server
nmap, |  web server, http and https are typical protocols that are used by servers, HTTP
	HTTP and HTTPS uses TCP. Tries to establish a connection using 3 way handshake
		SYN chronization, has specific sequence number from client to server
		SYN ACK and sends SYN and makes sure it is current requests with different seq number from server to client
		SYN ACK from Client

This is relevant to Nmap, because it sends a SYN and if it comes back as an ACK you know that port is opening and listening and what could be a vulnerability.
	Nmap -> sequence -> SYN scan complete


Nmap scan ACK
	client -> SYN -> Sever (this is typically blocked by most applications to protect and prevent vulnerabilities)
	Server -> SYN + ACK -> client

The way that Nmap gets around being blocked is that it pretends to be an already established connection. 
	It sends a fake SYN + ACK
	Server will send back a RST (reset) message if this occurs, which allows Nmap to come into play.

An XMAS scan is where you send all the flags as 1
	You are "lighting up the tree" or "flag fields"
	The idea is that the implementations get confused and may create a vulnerability

