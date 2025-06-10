# concepts
-Load balancing
-messaging queue - rabbit MQ, Zero MQ


#Architecture.
monolithic architecture
- ADvantages
- scales out.
- small team
- cohesive
- lesser moving parts
- faster(procedure calls) there is no RPC calls
- - Stackoverflow

-Disadvantages
- deploymenta are complicated.
- not decoupled
- too much responsibility on each server
- tight coupling

microservice architecture
client connected to gateway and connected to the server
- easier to scale
- interactive
- lesser parts are hidden
- microsoft


#Sharding in data base.
- horizontal partitioning, one key is used to break it into slices.(servers will be taking in the requests) SHARDING
- vertical partitioning, columns wise
- Take 1 attribute and partition the data so that database serevrs get each chunk.( normal servers are app data, platform servers)
- Consistency is important.
- availability also is important.
- UserID could be used for sharding the data.( Tinder uses location.)

 
 #Joins across the Shards, query goes into 2 diff shards.
 - JOINS - pull out the data from 2 diff servers/slices
 - Consistent hashing - used by memcached.
 - Fixed numbers of shards
 - manager to every shards to mini pieces inside shards.
 - Index - age < 35 years.
 - If there is a power failure, keep master slave architecture.
- Write request goes on masters.
- Reads request on slaves.
- NoSQL,indexing


#Single point of failure.
entire system crashes, if one part of system fails.
- Add another Node2 to Node1. which does the same thing, as a backup.if it was a database and every change is mirrored then it makes sense.
#More Nodes for servers.
#Master slave architecture for database.
- load balancer/gateway for connecting to wards the client and server
- make client connect to DNS and then to load balancer.
- 
#Regions if there is a disaster
 NETFLIX uses concept called as CHAOS MONKEY. goes and takes down one system server on production

#Content Delivery Network.
-DNS - 
-server Caching - keep the content in memory
-
#Event Driven services - persistent message(keep the msg, no loss)
- send request asynchronously.(request/response model)
- the scenario will be delayed
- so the Publisher - subscriber model (fire and forget) like (kafka/ rabbitMQ are examples are message broker)
- decopling the responsibilities.
- makes the system easier to understand.
- if new server is present, add it to message broker.
- Disadvantage -
- cant be used for mission critical systems, no idempotency.
- can be used for gaming services, twitter uses this model.
- 

#Event Bus handles the events.
- GIT uses events driven arch
- REACT uses event driven arc
- NODEJS uses event driven arc
- Gaming systems uses event driven arc
- Undo or move back option for events.

- servers stores the data in local, for availability.
- consistency is the question.
- Roll back operation is easy.
- New service is added.
- a) Replay from start b) store the diff c) undo

#No SQL Databases
- Diff between SQL and noSQL.
- SQL stores info in table format, address might be in diff table, join is expensive
- New attribute addition will result in adding locks to the table.
- ACID properties is adhered, foriegn key exists.
- are built for joins.

- NOSQL stores the data in the JSON format as blob, All data was written altogether
- NOSQL retrieving data altogether i.e insertion and retrieval will work on the entire data.
- easier to insert & retrive.
- scehma is flexible
- Adding new field is easy.
- horizontal partitioning is in built.
- built for scale, metrics
- Not built for updates
- ACID is not guaranteed.
- it is not read optimised.
- No implicit relations.
- Used during , no updates is required.

Cassandra cluster - load balancing , redundancy/ replication.
Qorum .
Elastic search - compaction


#API Design
GET, POST, PUT
Parameter definition, 
if response is bigger, then break it like TCP = 10, next 20, next 30...
Pagination and fragmentation.
Cache the info.


