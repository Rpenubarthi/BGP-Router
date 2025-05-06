# BGP Router Simulator

This is a simple Border Gateway Protocol (BGP) router implementation in Python. It simulates inter-domain routing behavior based on BGP-like message exchanges and policy-driven routing decisions. The router communicates with neighbors via UDP and handles route updates, withdrawals, path selection, and basic policy enforcement using customer, peer, and provider relationships.

## Features

- Supports update, withdraw, data, and dump messages over UDP sockets in a simulated environment.

- Maintains a dynamic routing table storing prefixes, masks, AS paths, origin types, and preference values for each route.

- Chooses the best route using multi-criteria decision-making: local preference, self-origin, AS path length, origin type, and peer tie-breaking.

- Aggregates contiguous routes to reduce routing table size, and disaggregates withdrawn prefixes when necessary.

- Honors BGP-like export rules depending on the relationship: customer, peer, or provider.

- Performs longest prefix match to forward data packets to the most appropriate neighbor.



## Implementation

### Message Processing:

- Handled and parsed various messages received (in JSON format)
  
### Routing Table Management:

- Maintained and updated a dynamic routing table.

- Implemented longest prefix matching to determine the optimal route.

- Supported route aggregation and deaggregation.

### Relationship Enforcement:

- Enforced routing policies based on customer, peer, and provider relationships.

### Packet Forwarding:

- Ensured accurate and efficient forwarding of data packets based on current routing state

## Usage

```bash
python3 router.py <ASN> <port-neighbor-relationship> [<port-neighbor-relationship> ...]

