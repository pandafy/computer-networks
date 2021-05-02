# Link State Packet(LSP)

Link state packet is a data structure that contains following information:

- **LSP.Router**: identification (address) of the sender of the LSP
- **LSP.age**: age or remaining lifetime of the LSP
- **LSP.seq**: sequence number of the LSP
- **LSP.Links[]**: links advertised in the LSP. Each directed link is represented with the following information: - LSP.Links[i].Id: identification of the neighbor - LSP.Links[i].cost: cost of the link


