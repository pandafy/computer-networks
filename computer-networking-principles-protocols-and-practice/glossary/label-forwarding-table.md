# Label Forwarding Table

- A *label forwarding table* is an array stored in memory of a network node.
- The label of incoming packet is the index to access this array.
- The lookup operation has O(1) complexity
- Each entry of the label forwarding table contains following details
  - the outgoing interface of the packet
  - the label for outgoing packet
