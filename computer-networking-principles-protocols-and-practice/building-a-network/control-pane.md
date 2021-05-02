# Control Pane

- Includes protocols and algorithms that are used to compute [forwarding tables](forwarding-table.md).

**Note:** While there is only one possible data plane for a given networking technology, different networks using the same technology may use different control planes.

The **simplest control pane** for a network is to **manually compute the forwarding tables for all routers** in the network.

### Shortcoming of Manual Computation of Forwarding Tables

1. It is not feasible to do for large networks
2. It makes it difficult to deal with link and router failures

### Alternative to manual computation of Forwarding tables

Use a network management software that updates the forwarding tables of the routers upon detecting a change in the network

**Shortcomings of using such software**
- It assumes that the management software will always capable to reach all routers even when the network topology is changed
- This may require a dedicated network that allows tha management platform to push information on the forwarding tables

### When to computer forwarding table?

**Calculating forwarding tables for the entire network**
- A widely used solution is to compute the entries of the forwarding tables for all destinations on all routers
- This ensures that each router has a valid route towards each destination. These entries can be updated when an event occurs and the network topology changes
- A **drawback** of this approach is that the forwarding tables can become large in large networks

**Caculating forwarding tables on requirement**

- Arrival of packets as the trigger to compute the corresponding entries
- If the destination is present in the forwarding table, the packet is forwarded.
- Otherwise, the router needs to find a way to forward the packet and update its forwarding table.

## Techniques used to maintain the forwarding tables

- [[distance-vector-routing]]
- [[Link State Routing]]

[//begin]: # "Autogenerated link references for markdown compatibility"
[distance-vector-routing]: distance-vector-routing "Distance Vector Routing"
[Link State Routing]: link-state-routing "Link State Routing"
[//end]: # "Autogenerated link references"