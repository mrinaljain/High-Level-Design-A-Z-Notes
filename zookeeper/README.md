# Zookeeper

Zookeeper is a configuration manager , that is internally a set of servers which contains files.

- Every Ephimeral node has an owner which creates the node.
- orchastrates the leader election

### Main components

- Nodes 

### Important terms
Ephepiral Nodes
:   Only owner can talk (read + writw) to its ephimeral node.

- Persistent Nodes

Heart beat :
: To remain the owner of the Ephimeral node the owner needs to keep sending heardbeat. if zookeeper doesnot get heartbeat then it will delete ephimeral file and start new leader elections.

Leader Election 
: Zookeper also is connected to master machine  

### Questions