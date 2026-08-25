Web and HTTP 

Quick review 

- Web page consists of objects, each of which can be stored on different web servers 
    

- object can be HTML file, JPEG image, Java applet, audio file... 
    

- Web page consists of base HTML-file which includes serveral referenced objects, each addressable by a URL, e.g, [www.someschool.edu/](https://www.someschool.edu/) (host name) someDept/pic.gif (path name) 
    

HTTP overview 

HTTP: hypertext transfer protocol 

- Web’s application-layer protocol 
    

- Client/server model: 
    

- Client: browser that requests, receives, (Using http protocol) and  
    

HTTP uses TCP: 

- Client initiates TCP connection (creates socket) to server, port 80 
    

- Server accepts TCP connection from client 
    

- HTTP messages (application-layer protocol messages) exchanged between browser (HTTP client) and web server (HTTP server)  
    

- TCP connection closed  
    

HTTP is stateless 

- Server does not care about past client requests 
    

Protocols that maintain state are complex 

- Past history is recorded 
    

- If the server or client crashes, their view maybe be wrong and might need to be adjusted 
    

3-way Handshake 

Before exchanging data, client and server must exchange packet information 

Client sends packet to server asking for connection 

This packet is called a request  

Some time passes 

Server sends back an accept connction 

Connection is established now 

client sends different packet, that contains HTTP request 

Server sends back a packet, named index.html 

HTTP connections: 

Non-persistent HTTP: 

1. TCP connection opened 
    

2. At most one object sent over TCP connection 
    

3. TCP connection closed 
    

Downloading multiple objects require multiple connections 

Persistent HTTP: 

- TCP connection opened 
    

- Multiple object can be sent over single TCP connection between that specific server and client 
    

- TCP connection closed 
    

Index.html  

[www.radford.edu](https://www.radford.edu)/index.html 

Host portion is [www.radford.edu](https://www.radford.edu) 

Path is index.html 

Object is inside the server 

Inside the index.html 

<html 

<a image.jpg 

/a> 

/html> 

1. Client opens HTTP connection to server at [www.someschool.edu](https://www.someschool.edu) on port 80 
    

2. HTTP server at host [www.someschool.edu](https://www.someschool.edu) waiting for connection on port 80, accepts connection, notifies client 
    

3. HTTP client sends request message 
    

4. HTTP server receives request message, forms response message containing object and sends message into socket 
    

5. Server closes TCP connection 
    

6. Client receives response, finds 10 jpeg objects 
    

7. Steps are repeated for each of 10 jpeg objects 
    

Steps 6 and 7 is the time where server can transmit a file 

HTTP response time (per object) 

- One RTT to create TCP connection 
    

- One RTT for HTTP request and bytes of HTTP response to return 
    

- Object/file transmission time 
    

Non-persistent HTTP response time = 2RTT file transmission time 

Round Time Trip - RTT (definition): Time for a small packet to travel from client to server and back 

RTT defines speed, whereas TTL dictates how many hops it can make 

RTT = 2 *(transmission delay + propagation delay)  

RTT = 2 (L / R + dist. / S) 

Persistent HTTP: 

Total response time = 2 RTT + File transmission time + Nx (RTT + File transmission time) 

Issues with non-persistent: 

Requires 2 RTTs per object 

OS overhead for each TCP connection 

Browsers often open multiple parallel TCP connections to fectch referenced objects in parallel. 

Persistent issues: 

Server leaves connection open after sending response 

HTTP messages after the first are sent over open connection 

Client sends request as soon as it encounters a referenced object 

As little as one RTT for all the referenced objects (cutting response time in half) 

Contains HTML file, small enough for negliglible transmission time, which references 8 equally small objects on the same server. How much time elapses from when the client clicks on the link until the client receives the object with: 

1. Non-persistent HTTP with no parallel TCP connections? 
    

Base HTML -> 8 referenced objects -> Objects are small 

File transmission time ~ 0 

Client request connection to server 

Server accepts, sends back confirmation 

Connection established – One RTT spent 

Client requests the object – HTTP get (base) 

Server sends the object 

Base file received  

Another RTT spent 

Connection required again 

Another RTT 

Client requests first object – image one 

Sever sends image 

Another RTT 

Client receives object 

Needs to repeat these 8 more times, so  

Total Response Time = 2 RTT + 8 (2 RTT) = 18 RTT 

2 RTT is a constant, Connection must be established first 

2. Non-persistent HTTP with 5 parallel TCP connections? 
    

3. Persistent HTTP? 
    

In the three-way handshake, does it mean each individual pixel is an object? 

In one download of a file in non-persistent could a singular packet carry a whole file or would there be several packets sent? 

Persistent HTTP connections – with pipelining 

1. Client initiates connection  
    

2. Server accepts the connection and ACK 
    

3. Client sends HTTP get for file 
    

4. Server receives request and transmits file 
    

5. Client receives entire document and reference to other files 
    

6. 6-8 client opens 5 parallel TCP connections one for each of the first 5 images. Each connection incurs a new RTT for the handshake and then another RTT for request/response. Bandwidth is shared equally among the 5 parallel transfers 
    

7. Server responds to the 5 requests 
    

8. Client receives entire file 
    

9. After files are received client opens 3 additional TCP connections for the remaining files. Each new connection requires RTT for handshake and request. Bandwidth is shared equally among the 3 active transfers 
    

L (bits)  

RouterA -> R(bps) / R(5) (bps) -> RouterB 

Persistent HTTP connections – with pipelining 

1. Client intiates single TCP connection to HTTP server 
    

2. Server accepts the connection and notifies the client with and ACK 
    

3. Client sends HTTP GET request for base object (in this example, index.html) 
    

4. Server receives the GET request, prepares the response containing index.html, and starts transmitting it without closing connection 
    

5. Client receives the first bits of index.html 
    

6. Client receives entire base html file and discovers references to other objects (e.g., images) 
    

7. Client sends multiple HTTP GET requests back-to-back for all referenced object (image1.jpg... image8.jpg) over the same TCP connection (pipelining) 
    

8. Server queues the pipelined requests and begins responding in order, following a First-come First-Served (FCFS) manner. (Response order must match request order in HTTP/1.1 pipelining) 
    

9. Client receives the responses for all objects (image1 -> image8) over the persistent connection, with no new handshakes required 
    

Without pipelining, you have to go back and forward, whereas with pipeline you make one request, and you get sent several files back without having to make several requests. That is after the connection is established, and the initial request is sent. 

In pipelining, after the initial base HTML is received, you can make a single request for several objects after that, and do not require anything else; the server sends everything (in separate packets) without having to make any more requests. 

Two different types of HTTP messages: Request, response 

- HTTP request message:  
    

- ASCII (human readable format)  
    

Request line (GET, POST, PUT, DELETE, HEAD) -> get (link) with carriage return character line-feed character. (in the example it is \r \h) 

Header lines follow after the first line, in paragraph format. 

Carriage return, line feed at start of the line indicates end of header line. This happens after the “paragraph.” Blank in the example 

Other HTTP request messages 

POST method: 

- Web page often includes from input 
    

- User input sent from client to server in entity body of HTTP POST request message 
    

GET method (for sending data server): 

- Include user data in URL field of HTTP GET request message (following a ‘?’): 
    

HEAD method:  

- Requests headers (only) that would be returned if specified URL were requested with an HTTP GET method. 
    

PUT method:  

- Up 
    

Status code appears in 1st line in server-to-client response mesage. 

Some sample codes: 

HTTP response codes:  

- 200 OK 
    

- Request succeeded, requsted object later in this message 
    

301 Moved permanently 

Request object moved, new location specificed later inthis message (in location: field) 

400 Bad requst 

Request msg not understood by server 

404 not found 

Request document not found on this server 

505 HTTP version not supported 

Maintaining user/server state: cookies 

Recall: HTTP GET/response interaction is stateless  

Web sites are client browser user cookies to maintain some state between transactions 

Four components: 

1. Cookie header line of HTTP response message 
    

2. Cookie header line in next HTTP request message 
    

3. Cookie file kept on user’s host, managed by user’s browsers 
    

4. Back-end database at Web site 
    

When maintaing the state, server provides a set cookie with specific identification, client keeps it and sends it back to the server when sending requests. Client keeps it for the entire duration after getting it and sends it back to the server, while keeping a copy on client 

What cookies can be used for:  

Authorization 

Shopping carts 

Recommendations 

User session state (web e-mail) 

Cookies and privacy: cookies permit sites to learn a lot about you on their site