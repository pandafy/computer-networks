# Addressing Scheme

Addressing Scheme of the data plane of the network depends on the datagram mode.

There are two types of addressing schemes
  - ## Flat
    - Each host and node has a unique address
    - **Unicity** is important for the functioning of the network
    - Used in networks where hosts and nodes are required to communicate immediately with unique address
    - Flat addresses are often embedded into the hardware by the manufacturer
    - **Advantage:**
      - supports ad-hoc and mobile networks
    - Lookup operation in the forwarding tables can be implemented based on exact match
    - When a packet arrives, the node has to check whether the destination address is part of the forwarding table
    - **[Content Addressable Memories]]** can perform the lookup efficiently at hardware level but their size is limited
    - **Disadvantages**
      - Size of forwarding tables increases linearly with the number of nodes and hosts
      -
  - ## Hierarchical
    - Reduces size of forwarding tables by creating hierarchy
    - Based on hierarchy of postal service
    - Allocation of network address should follow network topology
    - The **simplest** solution is to allocate one block of addresses to each network node and assign the host addresses from the attached host
    - **Drawbacks**
      - Lookups are more complex than flat addressing scheme
      - When a new host joins the network, it is required to communicate with some note to assign itself an address. This means some extra exchange of packets is required between network nodes and host
      - If host changes it's position in the network, it will get a new address. This could be problem for mobile networks
      - 
