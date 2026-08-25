[[cache]]
	once(any) name server learns mapping, it caches mapping, and immediately returns a cached mapping in response to a query
		Caching improves response time
		cache entries timeout (disappear) after some time (TTL)
		TLD servers typically cached in local name servers
	Cached entries may be out of date
		if named host changes IP address, may not be known internet-wide until all TTLs expire
		best-effort name-to-address translation
	