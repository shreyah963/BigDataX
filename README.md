# Creating a Distributed System Middle-ware: Implementing and Optimizing X-Search


## Overview
This technical report discusses the implementation of a multi-node architecture that facilitates X-Search and provides inter-node communication for transferring complex messages in a distributed system. The middleware aims to enable efficient information retrieval in parallel and distributed filesystems.

## Key Components
- Leader-worker model architecture
- TCP/IP-based socket communication
- Single-threaded non-blocking I/O using select()
- Complex message handling using:
  - Google Protocol Buffer
  - Network File System (NFS)
- X-Search integration with Borus library

## Implementation Details
- Leader node acts as moderator and handles connections from worker nodes
- Workers perform local indexing and searching
- File data stored in hash tables
- Tokenization and indexing process for search functionality
- Support for single term search queries

## Experimental Analysis
- Tests conducted on Mystic testbed using 5 torus nodes
- Performance evaluated across:
  - Varying number of indexing threads
  - Different node configurations 
  - Search latency using Protocol Buffer vs NFS
- Results showed millisecond-level search latencies across 32GB dataset

## Future Work
- Implement multi-threaded non-blocking I/O
- Add support for multi-term queries
- Enable multiple results per node
- Scale experiments to more nodes
- Optimize communication model

## References
The paper includes references to:
- Select() API documentation
- Google Protocol Buffer documentation
- Elasticsearch architecture
- Related work on scalable I/O and distributed systems

This research was conducted using the NSF-funded Mystic testbed.
