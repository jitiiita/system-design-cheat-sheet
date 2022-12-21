# system-design-cheat-sheet
System Design Interview Preparation Cheatsheet
What all we should prepare for System Design (High-Level Design) Interviews:

TOPICS/CONCEPTS
Vertical Scaling (Scale Up) Vs Horizontal Scaling (Scale Out)
Load Balancing & types - 
L3, L4, L7, Round Robin, Weighted Round Robin, IP Hash, Least Connections
Consistent Hashing
Monolithic Architecture Vs Service Oriented Architecture (SOA) Vs MicroServices Architecture
What is Single Point of Failure (SPOF)? When does it happen?
Non-functional requirements
Availability (High-availability, Fault tolerance, Resilience, Reliability)
Consistency
Durability
Maintainability
Performance (Latency, Throughput)
Scalability
Security
Observability (Metrics, Monitoring & Alarms)
Latency, Bandwidth, Throughput, Bottlenecks
Traffic Estimation, QPS, TPS, Read Write Ratio
Service Discovery & Health Checks
Idempotence in Systems
Stateful vs Stateless Systems (and their relation to Horizontal Scaling)
CAP Theorem
Consistency Vs Availability
Types of Consistencies: Weak, Eventual & Strong/Immediate Consistencies
Consistency models
Sequential consistency
Strict/Strong consistency/Linearlizability
Casual consistency
Eventual consistency (Monotonic reads, Monotonic writes, Read your own writes)
Read after write/create
Serializability
Database Concepts
Parititioning/Sharding
Indexing
Data Replication models - Master Master, Master Slave etc.
Data Replication types - Leader-based, Leaderless
Normalization vs Denormalization
Change Streams
SQL vs NoSQL
Characteristics: ACID vs BASE
OLTP vs OLAP
Types of NoSQL databases & their purposes
Document oriented
Wide Column,
Key Value
Graph
Which NoSQL database to choose when?
As per CAP theorem, we must choose from CA, AP or CP characteristics for a given system.
Choose K:V Stores if:
Simple schema
High velocity read/write with no frequent updates
High performance and scalability
No complex queries involving multiple keys or joins
Choose Document Stores if:
Flexible schema with complex querying
JSON/BSON or XML data formats
Leverage complex Indexes (multikey, geospatial, full text search etc)
High performance and balanced R:W ratio
Choose Column-Oriented Database if:
High volume of data
Extreme write speeds with relatively less velocity reads
Data extractions by columns using row keys
No ad-hoc query patterns, complex indices or high level of aggregations
Choose Graph Database if:
Applications requiring traversal between data points
Ability to store properties of each data point as well as relationship between them
Complex queries to determine relationships between data points
Need to detect patterns between data points

Data Caching
Eviction Policies - LRU, MRU, LFU, FIFO, LIFO, Random Replacement
Invalidation Policies - Read through, Write through, Refresh ahead, Write behind, Cache Ahead
What is TTL (Time to Live)?
What is Cache Miss? When does it happen?
Basic Components of a Distributed System
Content Delivery Network (CDN)
Load Balancer
Web Server Vs Application Server
IaaS (Infrastructure as a Service) vs PaaS (Platform as a Service) vs SaaS (Software as a Service) vs FaaS (Function as a Service)
Proxies - Forward Proxy & Reverse Proxy
API Gateway
Service Mesh Architecture
Communication Protocols
HTTP/HTTPS, REST, gRPC
REST vs gRPC for inter-service communication
Other protocols: SOAP, TCP, UDP, XMPP, AMQP, MQTT, STOMP, Openwire
Data structure formats
JSON, BLOB - Avro, Thrift, Ion, Protobuffs
Notification Mechanisms
Long Polling
Web Sockets
Messaging Queues & Why we need them
Back pressure in Message based systems
Event-driven architecture - How it supports decoupling, Event Handlers, Dead Letter Queues (DLQ)
What are data fan outs?
Point-to-point model vs Pub/Sub model
Push vs Pull model. Difference b/w them
What is a Poison Pill message?
What is a Data Pipeline? What do we use it for?
What are ETL Jobs? Why do we use them?
Batch Processing vs Stream/Real Time Processing of data
What are Cron Jobs? Why do we use them?
File Storage Vs Block Storage Vs Object Storage - Use cases of each one
Physical Machines vs Virtual Machines vs Containers as Hosts
Data Protection, Encryption at Rest, Encryption in transit, Principle of least privilege
Threat Modelling & Security concerns
Famous algorithms
Bloom Filter
Count Min Sketch
Geohash / S2 Geometry (Used in Uber Engineering)
Quadtree (Used in Uber Engineering)
Reverse index (Used in Web Crawlers like Google)

