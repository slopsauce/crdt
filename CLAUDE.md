# CRDT Chaos Visualizer - Claude Context

## Project Overview
This is an interactive web-based visualization tool for exploring Conflict-free Replicated Data Types (CRDTs). It demonstrates how distributed systems can maintain consistency despite network chaos.

## Technical Architecture
- **Single HTML file**: `chaos-counter.html` contains all code (HTML, CSS, JavaScript)
- **No dependencies**: Pure vanilla JavaScript implementation
- **G-Counter CRDT**: Implements a grow-only counter with state-based replication
- **GitHub Pages**: Deployed at https://slopsauce.github.io/crdt/

## Key Components

### CRDT Implementation
- `GCounter` class: Core CRDT logic with increment, merge, and value operations
- State-based replication: Nodes share their full state (`counts` object)
- Merge operation: Uses `Math.max()` to ensure convergence

### Visualization Features
1. **Three Nodes (A, B, C)**: Each maintains independent state
2. **Chaos Controls**: Drop rate, delays, duplicates, network partitions
3. **Auto-increment**: Automated testing with random intervals
4. **Convergence Graph**: Real-time visualization of node values over time

### Chaos Simulation
- **Drop Rate**: Randomly drops operations to simulate packet loss
- **Delays**: Adds random latency to operation propagation
- **Duplicates**: Tests idempotency by delivering operations multiple times
- **Partitions**: Completely isolates nodes from the network

## Development Notes
- When modifying, test with various chaos scenarios
- The graph updates every 100ms to show real-time convergence
- Partitioned nodes appear with dashed borders and reduced opacity
- Log entries are color-coded: green (success), orange (delay), red (drop)

## Future Enhancements to Consider
- Additional CRDT types (LWW-Register, OR-Set, 2P-Set)
- Operation visualization (show messages in transit)
- Persistence/save states
- More sophisticated partition scenarios
- Performance metrics and statistics