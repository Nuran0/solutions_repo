# Problem 1

# Algorithm for Calculating Equivalent Resistance Using Graph Theory

## Overview

To calculate the equivalent resistance of an electrical circuit using graph theory, we represent the circuit as a graph. The nodes in the graph represent junctions (or circuit nodes), and the edges represent resistors with weights equal to their resistance values. The algorithm simplifies the circuit step by step by reducing series and parallel resistors, ultimately calculating the equivalent resistance between two nodes.

## Algorithm Steps

### 1. Graph Representation
The circuit is represented as an undirected graph:
- **Nodes**: Represent junctions or components in the circuit.
- **Edges**: Represent resistors with resistance values assigned as weights.

The graph is constructed as follows:
$$
G = (V, E)
$$
Where:
- $V$ is the set of vertices (nodes),
- $E$ is the set of edges (resistors) with weights representing resistance values.

### 2. Identify Linear Chains for Series Reduction
In a series connection, resistors are connected end to end. The equivalent resistance of resistors in series is the sum of their resistances. To identify series connections:
- Traverse the graph using **Depth-First Search (DFS)** or **Breadth-First Search (BFS)**.
- If two resistors are connected linearly (i.e., one node connects them), reduce their resistance by summing the individual resistances.

For two resistors in series:
$$
R_{\text{eq}} = R_1 + R_2
$$
Where:
- $R_1$ and $R_2$ are the individual resistances.

### 3. Identify Cycles for Parallel Reduction
In parallel connections, resistors share the same two nodes. The equivalent resistance of resistors in parallel is given by:
$$
\frac{1}{R_{\text{eq}}} = \frac{1}{R_1} + \frac{1}{R_2}
$$
For $n$ resistors in parallel:
$$
\frac{1}{R_{\text{eq}}} = \sum_{i=1}^n \frac{1}{R_i}
$$

To detect parallel connections:
- Identify cycles in the graph where two or more resistors share the same pair of nodes.
- Use DFS to detect cycles and reduce the resistances accordingly by using the parallel resistance formula.

### 4. Iterative Simplification
- Start from any node and traverse the graph.
- In each iteration, detect series and parallel connections and reduce the resistances.
- Simplify the graph step by step until only one equivalent resistance remains between the two nodes.

### 5. Termination
The algorithm terminates when the graph has been reduced to a single equivalent resistance between the two terminal nodes of the circuit.


# Algorithm for Calculating Equivalent Resistance Using Graph Theory

## Overview

To calculate the equivalent resistance of an electrical circuit using graph theory, we represent the circuit as a graph. The nodes in the graph represent junctions (or circuit nodes), and the edges represent resistors with weights equal to their resistance values. The algorithm simplifies the circuit step by step by reducing series and parallel resistors, ultimately calculating the equivalent resistance between two nodes.

## Algorithm Steps

### 1. Graph Representation
The circuit is represented as an undirected graph:
- **Nodes**: Represent junctions or components in the circuit.
- **Edges**: Represent resistors with resistance values assigned as weights.

The graph is constructed as follows:
$$
G = (V, E)
$$
Where:
- $V$ is the set of vertices (nodes),
- $E$ is the set of edges (resistors) with weights representing resistance values.

### 2. Identify Linear Chains for Series Reduction
In a series connection, resistors are connected end to end. The equivalent resistance of resistors in series is the sum of their resistances. To identify series connections:
- Traverse the graph using **Depth-First Search (DFS)** or **Breadth-First Search (BFS)**.
- If two resistors are connected linearly (i.e., one node connects them), reduce their resistance by summing the individual resistances.

For two resistors in series:
$$
R_{\text{eq}} = R_1 + R_2
$$
Where:
- $R_1$ and $R_2$ are the individual resistances.

### 3. Identify Cycles for Parallel Reduction
In parallel connections, resistors share the same two nodes. The equivalent resistance of resistors in parallel is given by:
$$
\frac{1}{R_{\text{eq}}} = \frac{1}{R_1} + \frac{1}{R_2}
$$
For $n$ resistors in parallel:
$$
\frac{1}{R_{\text{eq}}} = \sum_{i=1}^n \frac{1}{R_i}
$$

To detect parallel connections:
- Identify cycles in the graph where two or more resistors share the same pair of nodes.
- Use DFS to detect cycles and reduce the resistances accordingly by using the parallel resistance formula.

### 4. Iterative Simplification
- Start from any node and traverse the graph.
- In each iteration, detect series and parallel connections and reduce the resistances.
- Simplify the graph step by step until only one equivalent resistance remains between the two nodes.

### 5. Termination
The algorithm terminates when the graph has been reduced to a single equivalent resistance between the two terminal nodes of the circuit.

