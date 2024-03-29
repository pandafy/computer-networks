# Network Layer

The main objective of the network layer is to allow endsystems, connected to different networks, to exchange information through intermediate systems called **router**. The unit of information in the network layer is called a **packet**.

The network layer enables the transmission of information between hosts that are not directly connected through intermediate routers

An example network where routers are represented by boxes and endsystems are represented by circles.

![](https://www.computer-networking.info/2nd/html/_images/tikz-62501f786ab0a69606c4982ab5a6396bd07c9bc1.png)

An important issue at network layer is the ability to identify a node. This is done by assigning an address to each node.

A **packet** contains additional data apart from the payload like sender and destination address.

Organizations for the network layer:
- [[Datagram Organization]]
- [[Virtual Circuit Organization]]

Functions of [[Control Protocols]] on network layer
- notifying source of the datalink layer bottlenecks downstream
- sending a control packet back to the source if a packet is received by a router that does not have a valid entry in its forwarding table
- sending a control packet back to the source if a router detects that a packet is looping inside the network
- verifying that packets can reach a given destination

[//begin]: # "Autogenerated link references for markdown compatibility"
[Datagram Organization]: datagram-organization "Datagram Organization"
[Virtual Circuit Organization]: virtual-circuit-organization "Virtual Circuit Organization"
[//end]: # "Autogenerated link references"
