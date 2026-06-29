# System Design Base
### How do you recognize between fundamentals vs patterns?

"Fundamentals= What systems are made of ". These are core primitives that explains how system scales.
Examples:
* ==Caching==
- ==Sharding==
- ==Replication==
- ==Partitioning==
- ==Load Balancing==
- ==Indexing==
- ==Consistent Hashing==

Examples:  
==Caching exists everywhere:==
- ==API responses==
- ==DB queries==
- ==CDN==
- ==session storage==
==It’s a primitive.==

"Patterns = How systems solve problems". It is a strategy to solve repeated problems.

Examples:
- ==Rate Limiting==
- ==Circuit Breaker==
- ==Message Queue==
- ==Event-Driven Architecture==
- ==Saga Pattern==
- ==Pub/Sub==

Example:  
==Rate limiting solves:==
- ==abuse prevention==
- ==traffic shaping==
- ==quota enforcement==
That’s a recurring solution.

---
