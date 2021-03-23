# Design-Distributed-Systems

Patterns and Paradigms for Scalable, Reliable Services

---

This repository is intended to quickly go through the various patterns from the book `Designing Distributed Systems by Brendan Burns (O’Reilly)`.
This has been created for study purpose only.

Supplemental material (code examples, exercises, etc.) is available for download at
https://github.com/brendandburns/designing-distributed-systems

## Introduction

- Distributed system applications are made up of multiple different applications
  running on different machines, or many replicas running across different machines. Building distributed systems is challenging.

- These distributed systems
  can be significantly more complicated to design, build, and debug correctly. The engineering
  skills needed to build a reliable distributed system are significantly higher
  than those needed to build single-machine applications.

- Containerized building blocks are the basis for the development of reusable components and patterns that dramatically simplify and
  make accessible the practices of building reliable distributed systems.

- Using containers and container orchestration as a foundation, we can establish a collection of patterns and reusable components. These patterns and components are a toolkit that we can use to build our systems more reliably
  and efficiently.

## Patterns

The different patterns are listed below:

- [Single Node Pattern](single-node-patterns/README.md)
