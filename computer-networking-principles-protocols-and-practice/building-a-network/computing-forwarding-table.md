# Computing Forwarding Table

### First technique

- Assumes that the underlying network topology is a tree.
- **Advantage of using tree topology:** There lies only one path between any pair of nodes in the network, it impossible to have forwarding loops in tree
- Node uses source/destination address from the packet to populate the forwarding table
- When a node receives a packet over a given interface, it learns that the source (address) of this packet is reachable via this interface.
- **[[Port Address Table]]**: data structure that maps each known source address to an incoming interface
- If the destination address is present in the port-address table, the packet is forwarded to respective interface to the nodes downstream until it reaches it's destination
- If the destination address has no entry in port-address table, it will send the packet to all of its interfaces except for the one on which the packet was received.
- **[[Broadcasting]]**: Forwarding a packet over all interfaces
- Broadcastng is a costly operation since packet will be sent over links that does not reach destination
- **Note:** In practice, the broadcasting operation does not occur often so the cost is limited.

_By inspecting the source and destination addresses of packets, network nodes can automatically derive their forwarding tables_

**Note:** _This technique is used in Ethernet networks

**Drawbacks of first technique**

- Packet sent to unknown destinations are broadcasted in the network even if the destination in not attached to the network
- If a cycle is present in the network, the broadcasting will saturate the bandwidth of the network.

**Note**: Network operators who are using port-address tables to automatically compute the forwarding tables also use distributed algorithms to ensure that the network topology is always a tree.

### [[Source Routing]]

- Enables destination to automatically discover paths from a given source towards itself.
- It requires nodes to modify the packet
- It is assumed that data plane can support two types of packets
  - data packets: used to exchange data
  - control packets: used to discover paths between two endhosts
- Source routing delegates heavy lifting from nodes to endhosts
- When a host or node starts, it sends special control packet over each of it's interface to advertise it's address to its neighbors.
- When a host or node receives such packet, it automatically replies with it's own address

**Note**: This kind of exchange can be useful to know whether the neighbor is still alive

- [[Source route]]: The data plane packets include a list of identifiers called **source route**
-
