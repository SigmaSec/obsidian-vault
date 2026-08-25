TLD servers: Responsible for .com, .org, .net, .edu, .aero, .jobs, .museums, and all top-level country domains, e.g.: .cn, .uk, .fr, .ca, .jp
When host makes DNS query, it is sent to its local DNS server
	Local DNS server returns reply, answering:
		From its local cache of recent name-to-address translation pairs (possibly out of date!)
		forwarding request into DNS hierarchy for resolution
	Each ISP has local DNS name server; to find yours:
		Windows: > ipconfig /all

[[DNS - Domain Name System]]