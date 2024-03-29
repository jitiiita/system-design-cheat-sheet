# system-design-cheat-sheet
System Design Interview Preparation Cheatsheet
What we should prepare for System Design (High-Level Design) Interviews:

# TOPICS/CONCEPTS
	- Vertical Scaling (Scale Up) vs. horizontal Scaling (Scale Out)
	- Load Balancing & types -  L3, L4, L7
 		- Application-layer algorithms
   			- Hashing, Endpoint evaluation
   		- Network-layer algorithms
			- Random selection, Round Robin, Weighted Round Robin,  Least Connections, IP hashing, Least pending requests
	- Consistent Hashing
 		- virtual nodes to avoid hotspot - using multiple hash functions, we can map one server multiple times on the ring
	- Monolithic Architecture Vs Service Oriented Architecture (SOA) vs. microservices Architecture
	- What is a Single Point of Failure (SPOF)? When does it happen?
	- Non-functional requirements
		- Availability (High-availability, Fault tolerance, Resilience, Reliability)
		- Consistency
		- Durability
		- Maintainability
		- Performance (Latency, Throughput)
		- Scalability
		- Security
		- Observability (Metrics, Monitoring & Alarms)
	- Latency, Bandwidth, Throughput, Bottlenecks
	- Traffic Estimation, QPS, TPS, Read Write Ratio
	- Service Discovery & Health Checks
	- Idempotence in Systems
	- Stateful vs. Stateless Systems (and their Relation to Horizontal Scaling)
	- CAP Theorem
	- Consistency Vs Availability
	
### Consistency models
	- Sequential consistency
	- Strict/Strong consistency/Linearizability
	- Casual consistency
	- Eventual consistency (Monotonic reads, Monotonic writes, Read your own writes)
	- Read after write/create
	- Serializability
 	- Tunable Consistency

## Database Concepts
	- Partitioning/Sharding
 		- Range-based partitioning, Range-based partitioning, Consistent Hashing
	- Indexing
	- Data Replication models - Master Master, Master-Slave, etc.
	- Data Replication types - Leader-based, Leaderless
	- Normalization vs Denormalization
	- Change Streams
	- SQL vs NoSQL
	- Characteristics: ACID vs BASE
	- OLTP vs OLAP
	
## Types of NoSQL databases & their purposes
	- Document oriented
	- Wide Column
	- Key Value  
	- Graph
	
### Which NoSQL database to choose when?
		- As per the CAP theorem, we must choose from CA, AP, or CP characteristics for a given system.
	
#### Choose K: V Stores if:
	- Simple schema
	- High velocity read/write with no frequent updates
	- High performance and scalability
	- No complex queries involving multiple keys or joins
#### Choose Document Stores if:
	- Flexible schema with complex querying
	- JSON/BSON or XML data formats
	- Leverage complex Indexes (multikey, geospatial, full-text search, etc)
	- High performance and balanced R:W ratio
#### Choose Column-Oriented Database if:
	- High volume of data
	- Extreme write speeds with relatively less velocity reads
	- Data extractions by columns using row keys
	- No ad-hoc query patterns, complex indices, or high levels of aggregations
#### Choose Graph Database if:
	- Applications requiring traversal between data points
	- Ability to store properties of each data point as well as the relationship between them
	- Complex queries to determine relationships between data points
	- Need to detect patterns between data points
	
### Basic Components of a Distributed System
	- Content Delivery Network (CDN)
	- Web Server Vs Application Server
	- IaaS (Infrastructure as a Service) vs PaaS (Platform as a Service) vs SaaS (Software as a Service) vs FaaS (Function as a Service)	
	- Proxies - Forward Proxy & Reverse Proxy
	- API Gateway
	- Service Mesh Architecture
	- Data structure formats
		- JSON, BLOB - Avro, Thrift, Ion, Protobuffs
	- Notification Mechanisms
		- Pull
		- Push
		- Long Polling
		- Web Sockets
	- Messaging Queues & Why we need them
	- Back pressure in Message based systems
	- Event-driven architecture - How it supports decoupling, Event Handlers, Dead Letter Queues (DLQ)
	- What are data fanouts?
	- Point-to-point model vs Pub/Sub model
	- Push vs. Pull model. Difference b/w them
	- What is a Poison Pill message?
	- What is a Data Pipeline? What do we use it for?
	- What are ETL Jobs? Why do we use them?
	- Batch Processing vs. Stream/Real-time Processing of data
	- What are Cron Jobs? Why do we use them?
	- File Storage Vs Block Storage Vs Object Storage - Use cases of each one
	- Physical Machines vs Virtual Machines vs Containers as Hosts
	- Data Protection, Encryption at Rest, Encryption in transit, Principle of least privilege
	- Threat Modelling & Security Concerns
	
### Data Caching
	- Query-Object Level, Client, CDN, Webserver, Database, Application
	- Eviction Policies - LRU, MRU, LFU, FIFO, LIFO, Random Replacement
	- Invalidation Policies - Read through, Write through, Refresh ahead, Write behind, Cache Ahead
	- What is TTL (Time to Live)?
	- What is Cache Miss? When does it happen?
	
### Communication Protocols
	- HTTP/HTTPS, REST, gRPC
	- REST vs gRPC for inter-service communication
 	- WebSocket, SSE, Long Polling
	- Other protocols: SOAP, TCP, UDP, XMPP, AMQP, MQTT, STOMP, Openwire
	
### Famous algorithms
	- Bloom Filter
	- Count Min Sketch
	- Geohash / S2 Geometry (Used in Uber Engineering)
	- Quadtree (Used in Uber Engineering)
	- Reverse index (Used in Web Crawlers like Google)
 ### Clocks
 	- Physical clock
  	- Lamport clock (logical)
   	- Vector clock




### WebSocket, Server-Sent Events (SSE), and Long Polling 
	- are three different techniques for enabling real-time communication and data exchange between a client (usually a web browser) and a server. Each has its own characteristics and use cases.

#### WebSocket:

	- Description: WebSocket is a full-duplex communication protocol that provides a persistent, bidirectional, low-latency connection between a client and a server. It enables real-time data exchange without the 	
 		overhead of HTTP 	
 	requests and responses.
	- Use Cases:
		- Real-time Chat Applications: WebSocket is commonly used for building chat applications and multiplayer games where low latency and real-time updates are essential.
		- Live Dashboards: WebSocket can be used to create live data dashboards that update in real-time.
	Advantages:
		- Low Latency: WebSocket offers minimal latency as the connection remains open.
		- Bi-Directional: Both the server and client can send data at any time.
		- Efficient: It reduces the overhead of HTTP requests and responses.
	Disadvantages:
		- Requires Server-Side Support: WebSocket requires server-side support for handling WebSocket connections.
#### Server-Sent Events (SSE):

	- Description: SSE is a unidirectional communication protocol that allows the server to push data to the client over a single HTTP connection. It's based on the EventSource API in JavaScript.
	- Use Cases:
		- Real-Time Notifications: SSE is suitable for applications that require real-time notifications, such as news updates or social media feeds.
		- Monitoring and Alerts: It can be used for monitoring systems and sending alerts when specific events occur.
	- Advantages:
		- Simplicity: SSE is easy to implement, especially on the client side.
		- Automatic Reconnection: SSE connections are automatically reestablished if they're interrupted.
	- Disadvantages:
		- Unidirectional: SSE only allows data to flow from the server to the client.
		- Limited Browser Support: SSE is supported in most modern browsers, but not all.
#### Long Polling:

	- Description: Long Polling is a technique where the client sends an HTTP request to the server, and the server holds the request open until new data is available. When new data is available, the server responds, 
 		and the client immediately sends a new request.
	- Use Cases:
		- Legacy Browsers: Long Polling can be used in scenarios where WebSocket or SSE are not supported, such as in older web browsers.
		- Real-Time Updates: It can be used for receiving real-time updates from the server.
	- Advantages:
		- Broad Compatibility: Long Polling works in a wide range of browsers and server setups.
		- Simple Implementation: It's relatively simple to implement compared to WebSocket.
	- Disadvantages:
		- Increased Server Load: Long Polling can result in higher server load due to the continuous open connections and repeated requests.
		- Latency: Long Polling introduces some latency because the server responds only when new data is available.

In summary, the choice between WebSocket, SSE, and Long Polling depends on your specific requirements and the compatibility of the technology with your target audience. WebSocket is ideal for low-latency bidirectional communication, SSE is suitable for unidirectional real-time updates, and Long Polling can be used when broader browser compatibility is needed but at the cost of increased server load and potential latency.




