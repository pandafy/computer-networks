# Piggybacking

- Reliable protocols needs to send data in both directions.
- A datalink entity can place the acknowledgements and the receive window that it advertises for the opposite direction of the data flow inside the header of the data frames that it sends


### Advantage

- It reduces the overhead by not requiring to send the entire frame just for acknowledgement

![https://www.computer-networking.info/2nd/html/_images/piggyback.png](https://www.computer-networking.info/2nd/html/_images/piggyback.png)

**Note**: The receiver will generate pure acknowledgement when it does not need to send data in the opposite direction.
