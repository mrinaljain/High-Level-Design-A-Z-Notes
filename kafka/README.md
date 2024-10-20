# Message Queues/Brokers AND Message Streams

Messaging Queues
: a queue which connects Application to a similar type of service


Messaging Steams
: A stream connects application to diffrent type of consumers and events can be sucscribed by any consumer.

### Features
- Helps to communicate Services and Applications Asynchronously.
- Acts as a buffer for the messages (provides a waiting area)
Example: Video Processing
- Brokers can retain buffer for N days
- Brokers are auto retry enabled

### Main components
Topics
:  Used to diffrentiate in diffrent types of event

Broker/Shard/Partition (Need to learn from naman bhalla)
:   multiple machines processing events
    Division of Topic based on size into diffrent brokers
    Partitions need to be defined by developer.

Replica
: Replica of data


Consumers/Subscribers
: Services that subscribe and pick events from queue

Producers/Publisers
: Applications that produce events and topics.

### Important points
- Its subscribers duty to delete the messsage from queue once processing is done.


### Dissadvantages

- some messages can be processed multiple times from Queus.


### Exercise
- Setup Rabit MQ locally
- write code to push messages

### Questions
- Diffrence between Message Queue and Message Streams?