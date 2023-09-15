# Consistent Hashing Implementation in Java

This repository contains a Java implementation of the consistent hashing algorithm, commonly used in distributed systems to efficiently distribute Requests/data across multiple nodes(Servers).

## Overview

The `ConsistentHashing` class provides the core functionality for the consistent hashing algorithm.

### Key Components:

#### Dependencies:
- `models.Node`: Represents a node in the system.
- `models.Request`: Represents a request with an associated ID.
- Various Java concurrent collections for thread-safe operations.

#### Attributes:
- `nodePositions`: A map that associates each node with its hash points.
- `nodeMappings`: A sorted map that links hash points to nodes.
- `hashFunction`: A function to compute the hash of a given string.
- `pointMultiplier`: A multiplier to determine the number of hash points for a node based on its weight.

#### Methods:
- `addNode(Node node)`: Adds a node to the system. For each node, it calculates multiple hash points based on the node's weight and the point multiplier. These points are then stored in the `nodePositions` and `nodeMappings`.
- `removeNode(Node node)`: Removes a node and its associated hash points from the system.
- `getAssignedNode(Request request)`: Given a request, it finds the appropriate node to which the request should be routed using the consistent hashing algorithm.

## Usage:

1. Create an instance of `ConsistentHashing` with a hash function and a point multiplier.
2. Add nodes to the system using the `addNode` method.
3. To route a request to a node, use the `getAssignedNode` method.
