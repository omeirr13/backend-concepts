# Intro
- We are either of jack of all trades(a master of none)
- master of vertical that we pick.
  
- We can taste fundametals, and while we are tasting, we find ourselves being gravitated towards one or one more..like database or being an expert in no-sql, high-scalabale and trasactional database engineer, which is quite niche.

## Communication protocols
- from lowlevel TCP, UDP, we can go lower(but then we going into networking aspect.
- why is udp connectionless vs why is tcp connectionfull.
- why is TCP slow

  And because we would understand why, we would make great decisions.

  - Higher concepts: HTTP/HTTPs
  - we will get in situation where we are building an API, our application is slow, and we have to know why opening 700 TCP connections is maybe a bad idea...if we dont know..we dont know why its slow.
  - websockets, why would i use bidirectional communication
  - gRPC, why was it invented?
 
  Anything that we see here, is invented because of a limitation of a previous protocol.

## Web Servers
- every single website we consume is hosted by web server.
- they have the ability to serve content.
- whether the content is static and we get in the ideas of caching
- or content is dynamic
- edge web servers?
- how webservers deal with etags, and their generation.
- and making sure caching mechanism of the client is actually correct
- how many threads does a web server has, is it single threaded like node js, or is it multithreaded like APACHE server.
- sometimes webserver do multiple jobs like:
- NGINX acts as a webserver and a proxy

## Database engineering
- indexes
- ACID(atomicity, consistency, isolation, and durability)
- noSQL dbs(maybe we dont want this rigid atomicity, we can give up some of these properties in favor of scalability)

## Proxies
- difference in proxy vs reverse proxy
- caching layers
- loading balancers
- TLS termination
- anything that makes a request on behalf of a client, anything that receives a request and makes a request to other servers that hide the identity of the original client, or hide identity of destination server.
- layer 7 proxy, layer 4 proxy, layer 3 proxy
- why do we have levels of proxy, what can we get at each layer.

## Caching layers
- caching important in both backend and frontend
- when to use caching
- stateful vs stateless caching
- cache eviction

## Messaging Systems
- becoming more important as we more towards interconnected system, there is no more that user connects to one system, there are system communicating with each other, so we need some type of messaging system to coordinate this thing.
- queue
- RabbitMQ
- Kafka(acts like a queue, but its a publish/subscribe system)
- we dont want to learn kafka, raabit mq these are tools/applications, mainly understand what is a messaging system, why did we build it.

## API Web Frameworks
- Node JS, Express JS, Django all are webframeworks designed to make web apis, rest apis, grpc

## Message Formats
- Protocol Buffers
- XML
- JSON

## Security
- encryption
- TLS(Transport layer security) between messaging and networking.
- how do you communicate between one node and other node so that communication is secure, so we stop man in the middle attacks, stop replay attacks
- how do we save our database credentials
- firewalls
- denial of service attacks
