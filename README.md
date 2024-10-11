## HLD

LoadBalancer

DNS

Domain Resolution

Reverse Proxying
: Jab request client se  kisi proxy server k through backend server pr ja rhi hai  to usko Proxy bolte hai.and jab request directly backend pr beji ho par backend ne khud ka proxy server laga rakho ho jo request redirection ko manage kr rahhai , usko revers proxy bolte hai.  

Load Balancing Algorithms ([read More...](https://samwho.dev/load-balancing/))
- Round Robin
- Weighted Round Robin
- Least Connections
- IP hashing 
- Weighted Least Connections
- Least Response Time
- peak exponentially weighted moving average

How load balancer comes to know that server has Died
   - HeartBeat
   - Healthcheck
Auto Scaling

Sharding Key

NAT (Network Address Translator)

MApping Sharde with users
 - modulus
 - Range based 

Consistent Hashing
- hashong
- adding, removing shard
- cascading failure
- solution of cascading Failure ( V Node)

Caching
: Storing precomputed data at some place so as to not fetch again from Database.
- global Cache
- loacl Cache(local app server itself)
- in-browser caching

Caching related Problem
- limited storage
- keep data sync
   - TTL

Netflix OpenConnect

### Cache sync policies
- Write Through (Through n through)
   - Server write on Cache
   - Server write on DB
   - if any fail then request failed  
   - if success then hurrey
- Write Back (backend sync DB)
   - write cache
   - give success
   - Asynchronously update DB in backend
- Write Around (around the cache)
   - Write DB first
   - then sync cache over the time.


CDN working
- Replication
- Anycast (Multiplexing)

Cache Eviction Strategies
- LRU
- LFU
- MRU
- LIFO
- FIFO


Lazy Invalidation

CAP Theorem
: Whenever there is a network partition in the distributed system, the system can either be consistentor Avaialbe.

PACELC Theorem
: Whenever there is a network partition in the distributed system, the system can either be consistentor Avaialbe.
else
When there is no network partition then system can be either Low latancy OR high consistant

Master-Slave Architecture
 - Master slave data sync
   - Incosistent
   - Eventuly Consistent
   - Highly Consistent
 
 - MAster slave Cons

 [TODO] Types of NoSQL DB 
 - Key Value DB
 - Document DB
 - Column Family (voice note available)
   - Data is stored Column wise
   - Reads are faster(can be used in red heavy systems)
   - Columnar Compression is possible.


Internals of No-SQL DB
   - Whan to create new shard ?
   - How Sharding happens
      - Consistent Hashing is used
   - Inserting New shard (voice note available)
      - create a shard.
      - calculate where shard needs to be placed
      - copy data to it
      - finally add it on hash ring.
   - Managing Consistency while creating new shard.
   - Managing Replication of Shards
      - Master - Slave Architecturw
         - Replication Factor
      - Multi Master
         - X : Replication Level
         - R : No. of machines to read from  ( R <= X )
         - No. of machines to write ( W <= X )
         -  R + W principal
         - Gossip Protocol

 Choosing Correct NiSQL DB
  - Just need single Key Value  ==> Key-Value DB
  - Schema is not final ==> Document DB
  - need analytics, only single column values = > Column Family DB
  
Storage Engine
- WAL
- WAL + Indexing
- compaction
LSM (https://www.scaler.com/academy/mentee-dashboard/class/231985/session)


Kafka
Zookeeper
HDFS
QuadTree
Geo Hashing
Microservices

185.42 101.6
109.22 104.14

window
114.3   104.14
