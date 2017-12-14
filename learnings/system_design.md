---
系统设计
---

> [HiredInTech](https://www.hiredintech.com/classrooms/system-design/lesson/55)

1. to clarify the system's constraints and to identify what use cases the system needs to satisfy.
    - 弄清楚系统的作用（并发量，统计要求，失效时间等限制和用途）
    - **Scope the problem: Don't make assumptions; Ask questions; Understand the constraints and use cases.**
2. outline all the important components that your architecture will need.(abstract design)
    - try to address every constraint and use case.
    - this sort of high-level design is a combination of well-known techniques, which people have developed.
    - **Sketch up an abstract design that illustrates the basic components of the system and the relationships between them.**
3. start thinking about what bottlenecks it has.
    - you need to be able to identify the weak spots in a system and be able to resolve them.
    - usually each solution is a trade-off of some kind, talk about them.
    - **Think about the bottlenecks these components face when the system scales.**
4. making your system scale.
    - **Address these bottlenecks by using the fundamentals principles of scalable system design.**
    - vertical scaling, horizontal scaling, caching, load balancing, database replication, database partitioning
    - Understanding these pros and cons, the advantages and disadvantages
    -
