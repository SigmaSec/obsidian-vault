- Mesh of interconnected routers 
    

- Packet-switching: hosts break application-layer messages into packets 
    

- Network forwards
    

Forwarding 

- Aka “switching” 
    

- Local action: move arriving packets from router’s input link to appropriate router output link 
    

Routing: 

- Global action: determine source-destination paths taken by packets 
    

- Routing algorithms 
    

Packet switching: store and forwards 

- Packet transmission delay: Takes L(ength)/R(ate) seconds to transmit (push out) L-bit packet into link at R(ate) bps 
    

- Transmission (d) = L/R sec 
    

- Store and Forward: entire packet must arrive at router before it can be transmitted on next link 
    

- One hop numerical example:  
    

- L = 10 Kbits 
    

- R = 100 Mbps 
    

- One-hop transmission delay = 0.1 millisecond 
    

- R1 cannot send another packet until the previous packets was sent. This would mean that R1 would have to wait until 0.1 msecs has changed before it can do anything else.  
    

Queue 

- Queue of packets waiting for transmission over output link 
    

- Queueing occurs when work arrives faster than it can be serviced 
    

When he is talking about delays, does this apply to both UDP and TCP or are we assuming that we are using TCP in this scenario? 

Packet queueing and loss: if arrival rate (in bps) to link exceeds transmission rate (bps) of link for some period of time: 

- Packets will queue, waiting to be transmitted on output link 
    

- Packets can be dropped (lost) if memory (buffer) in router fills up 
    

Alternative to packet switching: circuit switching: 

- End-end resources allocated to, reserved for “call” between source and destination 
    

- In diagram, each link has four circuits. 
    

- Call gets 2nd circuit in top link and 1st circuit in right link. 
    

- Dedicated resources: no sharing 
    

- Circuit like (guaranteed) performance 
    

- Circuit segment idel if not used by call (no sharing)  
    

- Commonly used in traditional telephone networks 
    

Frequency Division Multiplexing (FDM) Optical, electromagnetic frequency bands 

- Each call allocated its own band, can transmit at max rate of that narrow band 
    

Time Division Multiplexing (TDM) 

- Time divided into slots 
    

- Each call allocated periodic slot(s), can transmit at maximum rate of (wider) frequency band (only) during its time slot(s) 
    

Packet switching versus circuit switching 

- Example: 
    

- 1 Gb/s link 
    

- Each user: 
    

- 100 Mb/s when “active”  
    

- Active only 10% of time 
    

How many users can use this network under circuit switching and packing switching? 

1 G = 1000 M  

1 Gbps = 1000 Mbps 

1 Gbps / 100 Mbps 

How do packet delay and loss occur?  

- Packets queue in router buffers, waiting for turn for transmission 
    

- Queue length grows when arrival rate to link (temporarily) exceeds output link capacity 
    

Packet loss occurs when memory to hold queued packets fills up 

Packet delay: four sources 

Nodal = proc + queue + transmission + propagation 

- Nodal processing 
    

- Check bit errors 
    

- Determine output link 
    

- Typically < microseconds 
    

Queueing delay 

- Time waiting at output link for transmission 
    

- Depends on congestion level of router 
    

Transmission delay 

- L: Packet length (bits)  
    

- R: link transmission rate (bps)  
    

- Transmission delay formula = Length / Rate 
    

Propagation delay:  

- D: length of physical link 
    

- S: propagation speed (~2X10^8 meters/sec)  
    

- Propagation formula = distance  / speed 
    

- Example:  
    

- Router A is 1000km from Router B, we are traveling at 2 x 10^8 meters per second 
    

- Propagation = distance / speed = 1000 x 10 ^3 m / 2 x 10 ^ 8 m / s 
    

- 10 ^ 6 / 2 x 10 ^ 8 = 0.5 x 10 ^ -2 sec 
    

- 5 x 10^-3 sec 
    

Length of (physical) transmission array does not factor into delay of transmission time. 

Ethernet avoids propagation delay entirely 

Caravan analogy 

- How long does it take until the entire caravan is lined up before 2nd toll 
    

- Toll takes 20 seconds to service car 
    

- “Propagate” at 100mph 
    

- Distance is 100 miles 
    

- First car needs 1 hour and 20 second to get to the end.  
    

- So formula would be 20 (seconds) + 100 miles / 100 mph = 1 hour and 20 seconds 
    

- Suppose 10-car caravan  
    

- “propagate” at 1000mph, distance is 100 miles 
    

- Toll service time: one min to service a car 
    

- Will first car arrive to 2nd toll before all cars serviced at first toll? 
    

- Yes, after 7 mins first car arrives at second toll; three cars still at first booth 
    

- Formula will be 60(seconds) + 100 miles / 1000mph = 0.1 minute = 6 mins 
    

Example: 

- Assume the length of a packet is 8000 bits. The propagation speed on each link is 3 x 10 ^ 8 m/sec 
    

- Link 1: Transmission rate: 1000 mbps and Link length: 3 km 
    

- Transmission delay: 8000 bits / 1000 Mbps =  
    

- Propagation delay: 3000 / 3 x 10 ^ 8 m/sec = 10 ^ - 5 seconds = 10 microseconds 
    

- Link 2: Transmission rate: 1000 mbps and Link length: 500 km  
    

- Transmission delay: 8000 bits / 1000 Mbps 
    

- Propagation delay: 500000/ 3 x 10 ^ 8 m/sec = 1.67 microseconds 
    

- Link 3: Transmission rate: 1000 mpbs and link length: 1 km 
    

- Transmission delay: 8000 bits / 1000 Mbps = 8 x 10 ^ 3 bits / 10 ^ 9 bps = 8 x 10 ^ -6 sec = 8 microseconds 
    

- Propagation delay: 1000 / 3 x 10 ^ 8 m/sec = 3.3 microseconds 
    

- Transmission delay: 8 microseconds in each link 
    

- Link 1: 10 microseconds 
    

- Link 2: 1.67 microseconds 
    

- Link 3: 3.3 microseconds 
    

- 8 microseconds + 10 microseconds + 1.67 microseconds + 3.3 microseconds = 1.7074 milliseconds  
    

The actual math is not needed for exam/quiz but need to know the setup of the formula 

Example:  

- The end-to-end delay for one packet sent over a series of “N” links (ignoring the propagation delay)? 
    

- Router N * L / R to Nth router * L / R 
    

- The end-to-end delay for “P” packets sent over a series of “N” links (ignoring the propagation delay)? 
    

- 2 * length / rate where packet 1 is at router 2 and packet 2 is at router 1 
    

- N * L / R + 3 * (L / R)  
    

A 

- End – end Delay: ( N + P – 1) * transmission delay  
    

- Transmission delay = L / R 
    

Performance: loss, delay, throughput 

D -> 2d 

D(transmission) -> d(transmission)  

Transmission delay is determined by length of packet / rate (bps) 

Propagation delay is determined by the distance / speed 

Packet Size / Link’s rate (bandwidth) (speed) 

1. D' = 2d  
    

2. D’ = d 
    

Packet queueing delay 

A: Average packet arrival rate 

L: Packet length (bits)  

R: Link Bandwidth (bit transmission rate)  

L * A  

i = L * A / R – Arrival rate of bits / Service rate of bits “traffic intensity 

I = 0 -> small queueing 

I >= 1 -> Infinite 

La / R ~ 0: avg. Queueing delay small 

La / R -> 1: avg. Queueing delay larger 

La / R > 1: more “work” arriving is more than can be serviced – average delay infinite. 

I < o7 -> L * a / R <0.7 => 1 0x1,500 / 0.7 <R => <R= 150,000/ 

Queue (aka buffer) preceding link in buffer has finite capacity 

Packet arriving to full queue dropped (aka lost)  

Lost packet may be retransmitted by previous node, by source end system, or not at all 

Throughput: Rate (bits/time unit) at which bits are being sent from sender to receiver 

Instantaneous: rate at given point in time 

Average: rate over longer period of time 

R(s) < R(c) What is average end-end throughput? 

R(S) < R(c)  

10 connections (fairly) share backbone bottleneck link R bits/sec 

Throughput = min (Rs/R10 * Rc) 

Per-connection end-end throughput: min (RcRsR/10) 

In practice: R(c) or R(s) is often bottleneck 

Protocol layers are reference models 

Networks are complex with many pieces: 

- Host 
    

- Routers  
    

- Links of various media 
    

- Applications 
    

- Protocols hardware, software 
    

Question: is there any hope of organizing structure of network?  

Service model in layered internet 

Internet is organized as a stack of layers 

- To reduce design complexity 
    

- Ease of maintenance 
    

Service Model: 

- Each layer provides services to the layer above 
    

- The implementation details are abstracted (hidden), ensuring modularity and independence between layers. 
    

Client: 

5 Application layer 

Message – Network applications Communications  

4 Transport layer 

TCP Header -  Process-to-Process communication 

3 Network layer 

IP Header – Host – to – Host communication 

2 link layer 

MAC Header 

1 Physical layer