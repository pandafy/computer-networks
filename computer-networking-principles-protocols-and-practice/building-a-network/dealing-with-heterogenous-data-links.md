# Dealing with Heterogenous Datalinks

- The network layer deals with heterogenous datalink layers.
- **Example:** When a node receives a packet -> it decapsulates the packet ->   checks headers -> encapsulate it into another packet -> forwards the new packet
  - > When a node receives a frame, it decapsulates the packet that it contains, checks the header and forwards it, encapsulated inside another frame, to the outgoing interface.
- **Problems**:
  - Each datalink layer is characterized by a maximum size of the frame
  - Some operations is needed to be performed on frames to send them on datalink layer with smaller sized of frame
  - There could be three ways to deal with such problem

## Ways to deal with inconsistent data types:

![A simple heterogenous network](https://beta.computer-networking.info/syllabus/default/_images/tikz-2be59711e723184b601c2a2708ec85630a287b51.png)

A simple heterogenous network

### Discarding large frames

- If nodes find that it can not forward the incoming packet over the next link, it discards the packet.
- The node sends a control packet to the source to indicate the maximum allowed frame size of the next link
- The source could react to this control packet by retransmitting the information in smaller packet
- **Advantage:**
  - Network nodes remains simple as they don't require to fragment any packets
- **Disadvantage:**
  - Hosts needs to be complex
  - Increases the required buffer size in hosts
  - A host could need to retransmit a large packet several times it the maximum frame size decreases downstream. E.g. 1000 -> 800 -> 600
- > *This solution is used in the real world*

### Fragmenting and rebuilding frames at nodes
- **Fragmenting**:
  - The node finds out that it can not transmit the packet over the next link due to the size of the packet
  - It fragments the packet into smaller packets.
  - The header of there fragmented packets contains information of original source and destination.
- **Rebuilding**:
  - The subsequent node in the network rebuilds a new packet from these fragments if the next link supports sending bigger packets
- **Advantage:**
  - Packet is only fragmented for links where it is required
  - Larger packets can be used downstream of a link that only accept small packets
- **Disadvantage:**
  - Fragmenting packets at individual link increases processing time and buffer requirements of network nodes
  - Leads to longer end-to-end delay

### Fragmenting at node and rebuilding at host

- **Fragmenting**:
- The node finds out that it can not transmit the packet over the next link due to the size of the packet
- It fragments the packet into smaller packets.
- The header of there fragmented packets contains information of original source and destination.
- **Rebuilding**
  - The node does not rebuilds any packet.
  - The packet received by nodes downstream are simply forwarded to the next link if it supports
  - The fragmented packets are just as good as original packets
  - The destination hosts retrieves information from these fragmented packets
- **Advantage:**
  - Lower end-to-end delay
  - Requires fewer processing time and buffer memory on routers
- **Disadvantage:**
  - ??
