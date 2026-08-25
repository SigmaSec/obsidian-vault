[[DNS - Domain Name System]]
DNS services: 
	Hostname-to-IP-address translation
	Host aliasing
		Canonical, Alias names
	Mail server aliasing
	load distribution
		replicated web servers: many IP addresses correspond to one name
Canonical Hostname -> relay1.example.com -> Alias -> example.com
[[client]] queries root server to find .com DNS server
