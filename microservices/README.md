# Microservices

Multiple diffrent isolated machines working collectivle to make a web application work.

### Components
API Gateways
: API Gateway is an infrastructure layer that works alongside loadbalancer which decides that which microservice needs to process the request.

---
## Molecular vs Microservices

### Microservices
- Code is splited into multiple reposotries
- ==Selective Scaling== services can be pushed live
- Cross service communication is expensive
- Developer onboarding is difficult
- Testing is difficult
- Cost is Expensive
- ==Feature isolation== is possible
- Use of multiple language is possible
- Compilation time is less
- Latancy is high
- More work for DEvops

### Monolith Architecture
- Code is in single Repository
- complete app needs to be pushed live
- Cross service communication is not expensive
- Developer onboarding is easy
- Testing is easy
- Cost is less
- Feature isolation is not possible
- Can not use multiple languages
- Compilation time is huge
- Latancy is low
- Less work for DevOps

---

### Communication between Microservices

1. Asynchronous Communication
   - Uning Messaging Queues/ Streams

2. Synchronous Communication
   - HTTP 
      - Normal API calls
   - RPC (Remote Procedural Calls)
      - Internal API calls using Protobuffs
      - [More about Protobuffs](https://protobuf.dev/)

### Observablity in Microservices [Error tracking]
1. Distributed Tracking
   By adding request id to each request
2. Logs Pooling
3. Alerting ()

### Maintaining Consistency between Microservices

Example:
- Maintaining Consistency during Distributed Transactions
   - Technique 1 => **~~Two Phase Commit~~**
   Put  lock on both ends => make changes and then unlock.
   Dissadvantages:
      - we can reach starvation
      - It is an Antipattern
   

   - Technique 2 => **SAGA PAttern**
   Evert step has a rollback feature available
   SAGA can be implemented/executed by two types
      - Orchestration
         - Central cordinator is appointed
         - SPOF
         - Easy to implement
         - Fast
      - Coreography
         - Works on collective decision
         - Difficult to implement
         - Slow
### Design Patterns
 A very accepted solution to commenly occuring software design problems.

- **CQRS** (Responsibility Segregation)
   - Other common microservice is created
- **Circuit Breaker** Pattern [Page 111]
   - Cascading Failure
   - Thundering Attack
   - Down, Recovery, Up

### Questions
- Diffrence between monolith/ microservices
- Diffrence between microservice / serviceoriented
- Solve pretty- json question on interview bit
- Bank transactions are ATOMIC ?