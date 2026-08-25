	Peer-Peer architecture 

- No always-on server 

- Arbitrary end systems directly communicate 
- Peer request services from other peers, provide service in return to other peers 
    

- This allows for self-scalability – new peers bring new service capacity, as well as new service demands 
- Peers are intermittently connected and change IP address 

- Complex management 
Processes communicating 

Process: program running within a host 

- Within same host, two processes communicate using inter-process communication (defined by OS)  
    

- processes in different hosts communicate by exchanging messages 
    

Clients, servers 

- Client process: process that initiates communication 
    

- Server process: process that waits to be contacted 
    

Sockets 

- Process sends / receives messages to / from its socket 
    

- Socket analogous to door 
    

- Sending process shoves message out of door 
    

- Sending process relies on transport infrastructure on other side of door to deliver message to socket at receiving process 
    

- Two sockets involved: one on each side 
    

- To receive message, process must have identifier 
    

- Host device has unique 32-bit IP address 
    

- Q: does IP address of host one which process runs suffice for identifying the process?  
    

- A: no, many processes can be running on same host 
    

- Identifier includes both IP adress and port numbers associated with process on host 
    

- Example port numbers: 
    

- HTTP server: 80 
    

- Mail server: 25 
    

An application-layer protocol defines:  

- Types of messages exchanged, 
    

- E.g., request, response 
    

- Message syntax: 
    

- What fields in messages and how fields are delineated 
    

- Message semantics 
    

- Meaning of information in fields 
    

- Rules for when and how processes send and respond to messages 
    

Open protocols:  

- Definined in RFCs, everyone has access to protocol definition 
    

What transport services does an app need?  

Reliable data transfer 

- Some apps require 100% reliable data transfer 
    

- Other apps (can tolerate some loss 
    

Timing 

- Some apps require low delay to be “effective”  
    

Internet transport protocols services  

TCP: 

- Reliable transport between sending and receiving process 
    

- Flow control: sender won’t overwhelm receiver 
    

- Congestion control: throttle sender when network overloaded 
    

- Connection-oriented: setup required between client and server processes 
    

- Does not provide timing, minimum throughput guarantee, security 
    

UDP:  

- Unreliable data transfer between sending and receiving process 
    

- Does not provide reliability, flow control, congestion, control, timing, throughput guarantee, security, or connection setup