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
  
