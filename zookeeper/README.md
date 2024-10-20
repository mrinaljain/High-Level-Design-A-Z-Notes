# Zookeeper

Zookeeper is a configuration manager , that is internally a set of servers which contains files.

#### Problemes to be solved
- extra hop to get configurations
- SPOF
- Leader Election

### Working  of zookeeper
- Every Ephimeral node has an owner which creates the node.
- orchastrates the leader election
- Zookeeper is connected to master machine, It informs whenever IP chaanges .

### Main components

- Nodes
  - ephimeral nodes
  - persistent nodes

### Important terms
Ephepiral Nodes
:   Only owner can talk (read + writw) to its ephimeral node.

- Persistent Nodes

Watch Setup
: servers other then master are into watch list

Heart beat :
: To remain the owner of the Ephimeral node the owner needs to keep sending heardbeat. if zookeeper doesnot get heartbeat then it will delete ephimeral file and start new leader elections.

Leader Election 
: Zookeper also is connected to master machine. slave who writes first becomes leader
[More about leader Election](https://www.quora.com/How-is-a-leader-elected-in-Apache-ZooKeeper)

### Questions