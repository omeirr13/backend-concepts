# TCP Handshake
- a very important technology that engineers should understand.
- lets say im doing a curl request or an http request or we have a browser and we want to visit a page.
- the first thing that happens a TCP Connection is established
- we are about to send a get request, get request has headers cookies
- eventually it will turn into packets, and we are going to send these packets one after the other.

- these packets will arrive at the server, server will pick them up, and see its a get request and then try to process it.
### what if a packet didnt arrive?
- how does client know that packet didnt arrive.
- we need to introduce the concept of acknowledgement.
- each packet must be followed by an acknowledgement from server, hey i have received this packet. and if client doesnt receive aknowledgement that this particular packet has not arrived, then client retranmits it, otherwise we would run into corruption all the time.
### How do we identify a packet?
- each packet needs to have a unique identifier, and this is called a sequence number
- server will wait for all the packets first, and it will start reordering it if not in sequence, if it does not have numbers, it cant order..thats why sequence numbers.

### How does server know packet no. 7 is first packet..or 6 is the first packet?
- Here comes the step that we require to agree between server and the client called synchronization.
- both have to agree on sequence numbers, because client will have own sequence number and server its own...thats why we need TCP handshake.

- the cleint need to agree on a sequence, client sends a SYN packet to the server to indicate it wants to establish connection.
- the server responds with SYN-ACK packet, acknowledging the clients sequence number..Got your SYN with seq 1000.. server also provides into own starting sequence number.
- client sends a ACK packet back to the server, confirming receipt of the servers sequence numbers..
- now, both the client and server are synchronized with each other's sequence numbers, and data transfer can begin.
- then we start with a get request

### why cant we start from a known number? like 0?
- Starting with a fixed number like 0 would be predictable and insecure. An attacker could guess the sequence number and inject malicious packets (known as a TCP sequence prediction attack). Randomizing the starting sequence number enhances security and prevents such attacks.