Caching example: 

Access link rate: 1.54 Mbps 

RTT from internet router to server: 2 sec 

Web object size: 100k bits 

Average request rate from browsers to origin servers: 15 req/sec 

Avg data rate to browsers: 1.50 Mbps 

LAN delay ~ 0 + Access Delay (?) + Internet Delay (2 sec) 

D = L / R = 100 * 10^3 bits / 1 * 10^9 bps = 10^5 / 10^9 = 10^- 4 = 0.1 msec 

I = L * a / R = (100 * 10^3 [bits] * 15 req/sec) / 1.54 * 10^6 [bps] = 1.5 * 10 ^ 6 / 1.54 * 10^6 = 0.97 

This is bad as it is approaching 1, queueing delays is at high utilization 

LAN utilization = .0015 

End-end delay = internet delay + access link delay + lan delay = 2sec + mins + usecs 

Instead of improving the access delay (expensive)  

User configures browser to point to a local web cache 

We can cache data.  

If object in cache, cache return objects to client 

Else cache requests object from server, caches received object, and then returns object to client 

Suppose that caching is at 40% requests, with low delay 

15 requests reduces to .6 * 15 = 9 requests per second 

So overall util is 0.97 * .6 = 0.58. Much better, this is more normalized queueing delay 

Average end to end is .6 * (delay of origin servers) + .4 * (delay when satisfied at cache) + .6 (2.01)  + .4 (~msecs) =~ 1.2 sec 

Problem with this is that matinence is high, passwords would end up getting cached, which is a security vulnerability. 

Another option is to send a lower prio packet, add to headers to the packet 

Web cache – server 

HTTP response 

Last.modified 

Stores last modified date on the server 

Client asks for object – 1  

Server checks for “if modified since : timestamp” 

304: not modified (outdated timestamp) 

Server wants to send – 200: ok 

Web cache acts as both client and server 

Server tells cache about object allowable caching in response header: 

Cache-control: max – age = <seconds> 

Cache – control: no – cache 

Why web caching?  

Reduce response time for client request 

Reduce traffic on institution's access link 

Internet is dense with caches 

Conditional get- goal: don’t send object if cache is up to date cached version 

HTTP1.1: introduced multiple pipelined GETs over single TCP connection 

Server responds in FCFS 

With FCFS, small object may have to wait for transmission (Head-of-line (HOL) blocking) behind large objects 

Loss recovery (retransmitting lost TCP segments) stalls object transmission 

HTTP/2: increased flexibility at server in sending objects to client