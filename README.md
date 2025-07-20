# CRDT Chaos Visualizer 🐵🤖

An interactive visualization tool for exploring Conflict-free Replicated Data Types (CRDTs) and their behavior under chaotic network conditions.

## Live Demo

Visit the live demo at: [https://YOUR-USERNAME.github.io/crdt/](https://YOUR-USERNAME.github.io/crdt/)

## Features

- **G-Counter CRDT Implementation**: A grow-only counter that demonstrates basic CRDT principles
- **Chaos Controls** 🐵:
  - Drop Rate: Simulate packet loss
  - Delays: Add network latency
  - Duplicates: Test idempotency
  - Network Partitions: Isolate nodes completely
- **Auto-Increment** 🤖: Automated testing with configurable intervals
- **Real-time Convergence Graph**: Visualize how nodes converge over time
- **Interactive Nodes**: Three independent nodes (A, B, C) that sync their state

## What are CRDTs?

CRDTs are data structures that can be replicated across multiple nodes in a distributed system, where each replica can be updated independently and concurrently without coordination. Despite network failures, delays, or partitions, CRDTs guarantee eventual consistency - all nodes will converge to the same state once they can communicate.

## How to Use

1. **Manual Testing**: Click "Increment" on any node to increase its counter
2. **Automated Testing**: Use "Start Auto-Increment" to make nodes increment automatically
3. **Add Chaos**: Adjust the chaos controls to simulate real network conditions
4. **Create Partitions**: Isolate nodes to simulate network splits
5. **Watch Convergence**: The graph shows how nodes diverge and reconverge

## Experiments to Try

1. **Perfect Network**: Start with no chaos - watch perfect synchronization
2. **Packet Loss**: Set 50% drop rate - see how nodes handle missing updates
3. **Network Partition**: Isolate Node A, let others continue, then reconnect
4. **Chaos Storm**: Max out all chaos controls and watch CRDTs maintain consistency
5. **Partition Healing**: Create divergence, then remove all chaos to see convergence

## Technical Details

This visualizer implements a G-Counter (Grow-only Counter) CRDT using:
- State-based replication (nodes share their full state)
- Vector clock-like structure (each node tracks its own count)
- Merge operation using `max()` for convergence

The implementation demonstrates key CRDT properties:
- **Commutativity**: Order of merges doesn't matter
- **Associativity**: Grouping of merges doesn't matter
- **Idempotency**: Merging the same state multiple times is safe

## Local Development

Simply open `chaos-counter.html` in a web browser. No build process or dependencies required!

## Learn More

- [The Evolution of CRDTs](evolution%20of%20crdts.md) - A comprehensive overview of CRDT technology
- [CRDT Tech](https://crdt.tech/) - Introduction to CRDTs
- [Wikipedia: CRDT](https://en.wikipedia.org/wiki/Conflict-free_replicated_data_type)