# 8x8 Mesh vs Torus vs Fat Tree Topology Comparison

This repository presents a performance comparison of three 8x8 Network-on-Chip (NoC) topologies:

* 8x8 Mesh
* 8x8 Torus
* 8x8 Fat Tree

The comparison focuses on how latency changes with increasing injection rate and how the different topologies behave as the network approaches saturation.

## Performance Metrics

### Injection Rate

Injection rate represents the rate at which packets are injected into the network. Increasing the injection rate increases the amount of traffic being generated and places a higher load on the network.

### Latency

Latency is the time taken for a packet to travel from its source to its destination. Under low traffic conditions, latency generally remains relatively stable. As congestion increases, packets spend more time waiting in queues, resulting in higher latency.

## Topologies

### 8x8 Mesh

The 8x8 Mesh consists of 64 nodes arranged in an 8x8 grid, with nodes connected to their neighboring nodes. It provides a simple and regular network structure, but its limited connectivity can result in congestion at relatively low injection rates.

### 8x8 Torus

The 8x8 Torus extends the mesh by adding wrap-around connections between opposite edges of the network. These additional paths improve connectivity and allow the network to handle a higher traffic load before saturation.

### 8x8 Fat Tree

The 8x8 Fat Tree uses a hierarchical structure with increased bandwidth toward the higher levels of the tree. This additional connectivity helps reduce bottlenecks and allows the topology to support significantly higher injection rates.

### Saturation Point

The saturation point is the region where the network can no longer efficiently handle the increasing traffic load. It is identified by the sharp rise in latency as the injection rate is increased.

From the obtained results, the approximate saturation points are:

* Mesh: around 0.007 injection rate
* Torus: around 0.26 to 0.27 injection rate
* Fat Tree: around 0.70 to 0.75 injection rate

These values indicate that the Fat Tree can sustain the highest injection rate before severe congestion occurs, followed by the Torus and then the Mesh.

## Comparison

The results show a clear difference in saturation behavior. The Mesh saturates earliest at approximately 0.007, while the Torus reaches saturation around 0.26 to 0.27 and the Fat Tree around 0.70 to 0.75.

Overall, the Fat Tree handles the highest injection rate before severe latency increase, followed by the Torus and then the Mesh.

## Key Observations

* The Mesh experiences a sharp increase in latency at a much lower injection rate.
* The Torus handles substantially more traffic before latency rises sharply.
* The Fat Tree maintains relatively stable latency over the largest injection rate range.
* The overall traffic handling capability is Fat Tree > Torus > Mesh.

## Conclusion

This project compares the latency and saturation behavior of 8x8 Mesh, Torus, and Fat Tree topologies. The results show that topology has a significant impact on network performance under increasing traffic.

Among the three, the Fat Tree provides the highest saturation threshold, followed by the Torus, while the Mesh reaches saturation at the lowest injection rate.
