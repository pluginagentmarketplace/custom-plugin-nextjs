---
name: architecture-skills
description: Master system design, architecture patterns, algorithms, data structures, and computer science fundamentals for building scalable systems.
---

# System Architecture & Design Skills

## Big O Complexity Analysis

```
Time Complexity:
O(1)      - Constant (best)
O(log n)  - Logarithmic
O(n)      - Linear
O(n log n)- Linearithmic (sorting)
O(n²)     - Quadratic
O(n³)     - Cubic
O(2ⁿ)     - Exponential
O(n!)     - Factorial (worst)

Space Complexity: Same analysis
```

## Common Data Structures

```
Array:      O(1) access, O(n) insert/delete
Linked List: O(n) access, O(1) insert/delete
Hash Table: O(1) average, O(n) worst
Binary Tree: O(log n) balanced, O(n) worst
Graph:      O(V + E) traversal
```

## Sorting Algorithms

```python
# Quick Sort - O(n log n) average
def quicksort(arr):
  if len(arr) <= 1: return arr
  pivot = arr[0]
  left = [x for x in arr[1:] if x < pivot]
  right = [x for x in arr[1:] if x >= pivot]
  return quicksort(left) + [pivot] + quicksort(right)

# Merge Sort - O(n log n) guaranteed
def mergesort(arr):
  if len(arr) <= 1: return arr
  mid = len(arr) // 2
  left = mergesort(arr[:mid])
  right = mergesort(arr[mid:])
  return merge(left, right)
```

## Design Patterns

```
Creational:
- Singleton: Single instance
- Factory: Create objects
- Builder: Complex object construction

Structural:
- Adapter: Interface compatibility
- Decorator: Add functionality
- Facade: Simplified interface

Behavioral:
- Observer: Notify subscribers
- Strategy: Interchangeable algorithms
- State: Object state changes
```

## System Design Principles

```
SOLID:
S - Single Responsibility
O - Open/Closed
L - Liskov Substitution
I - Interface Segregation
D - Dependency Inversion

DRY - Don't Repeat Yourself
KISS - Keep It Simple Stupid
YAGNI - You Aren't Gonna Need It
```

## Scalability Patterns

```
Vertical Scaling:
- Add more CPU/RAM
- Easier, but limited
- Single point of failure

Horizontal Scaling:
- Add more servers
- Load balancing needed
- Better resilience

Caching Strategies:
- Client cache
- CDN cache
- Application cache (Redis)
- Database cache

Database Scaling:
- Read replicas
- Sharding
- Partitioning
```

## Distributed Systems Concepts

```
CAP Theorem:
- Consistency
- Availability
- Partition tolerance
(Choose any 2 of 3)

Consensus Algorithms:
- Paxos
- Raft
- Byzantine Fault Tolerance

Eventual Consistency:
- Allows temporary inconsistency
- Better availability
- Used in NoSQL databases
```

## API Design Principles

```
REST:
- Use HTTP methods correctly
- Resource-oriented URLs
- Stateless
- Standard status codes
- Versioning strategies

GraphQL:
- Query language for APIs
- Request exactly what you need
- Strongly typed schema
- Real-time subscriptions
```

## Security Architecture

```
Defense in Depth:
1. Network security (Firewalls, WAF)
2. Application security (Auth, validation)
3. Data security (Encryption, hashing)
4. Access control (RBAC, ABAC)

OWASP Top 10:
1. Injection attacks
2. Broken authentication
3. Sensitive data exposure
4. XML external entities
5. Broken access control
6. Security misconfiguration
7. Cross-site scripting (XSS)
8. Insecure deserialization
9. Using vulnerable components
10. Insufficient logging
```

## Performance Optimization

```
Frontend:
- Code splitting
- Lazy loading
- Caching (HTTP, browser)
- CDN distribution
- Image optimization

Backend:
- Database indexing
- Query optimization
- Connection pooling
- Caching (Redis)
- Async processing

Monitoring:
- APM tools
- Distributed tracing
- Log aggregation
- Alerting
```

## Key Concepts Checklist

- [ ] Big O complexity analysis
- [ ] Data structure trade-offs
- [ ] Sorting and searching
- [ ] Graph algorithms
- [ ] Dynamic programming
- [ ] System design interviews
- [ ] Scalability patterns
- [ ] Database design
- [ ] Caching strategies
- [ ] Load balancing
- [ ] Microservices
- [ ] API design
- [ ] Security principles
- [ ] Performance optimization

---

**Source**: https://roadmap.sh
