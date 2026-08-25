DNS: Distributed database storing resource records (RR)
	RR format: (name, value, type, ttl)
Type = A 
	name is hostname
	value is IP address
Type = NS 
	Name is domain (e.g., foo.com)
	value is hostname of authoritative name server for this domain
Type = CNAME
	name is alias name for some "canonical" (the real) name 
	www.ibm.com is really servereast.backup2.ibm.com
	value is not canonical name
Type = MX