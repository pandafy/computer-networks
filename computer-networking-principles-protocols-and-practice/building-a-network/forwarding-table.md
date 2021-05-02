# Forwarding Tables

 A forwarding table is a data structure that maps each destination address (or set of destination addresses) to the outgoing interface over which a packet destined to this address must be forwarded to reach its final destination.

 The computation of the forwarding tables of all the routers inside a network is a key element for the correct operation of the network.

 In a network, a path can be defined as the list of all intermediate routers for a given source destination pair

 If forwarding tables are not correctly computed, it can give rise to two kind of problems

 - **Black Hole**
   - A black hole is a router which recieves packet for atleast one destination/source pair, but does not have any entry inside its forwarding table for the given destination address.
   - The router could not forward the packet and does have to discard them
   - The algorithm which computes the forwarding table should make sure that there are no black holes in the network.
 - **Forwarding loop**
   - When a packet is keeps getting forwarded between routers and could not reach its destination

**Note:** A forwarding loop is more problematic than a black hole because the packets being forwarded keeps utilizing the bandwidth of the network. The worst case for black hole is packet getting discarded.

_Any solution which is used to compute the forwarding tables of a network must ensure that all destinations are reachable from any source. This implies that it must guarantee the absence of black holes and forwarding loops._


