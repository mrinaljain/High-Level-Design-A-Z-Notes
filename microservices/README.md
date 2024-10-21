# Microservices

Multiple diffrent isolated machines working collectivle to make a web application work.

## Components
API Gateways
: API Gateway is an infrastructure layer that works alongside loadbalancer which decides that which microservice needs to process the request.


## Communication between Microservices

1. Asynchronous Communication
   - Uning Messaging Queues/ Streams

2. Synchronous Communication
   - HTTP 
   - RPC (Remote Procedural Calls)



---
- Molecular vs Microservices

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



### Questions
- Diffrence between monolith/ microservices
- Diffrence between microservice / serviceoriented