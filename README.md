# Event-Driven Activity & Notification Platform

A scalable backend platform designed to process user activities asynchronously using event-driven architecture.

This system demonstrates:
- Kafka-based event processing
- Redis caching strategies
- GraphQL API gateway
- PostgreSQL relational modeling
- Horizontal scalability design

## Problem statement:

Modern applications require real-time activity processing, notification systems, and feed aggregation at scale. 
Synchronous processing tightly couples components and increases latency. 
This project explores an event-driven architecture to decouple activity ingestion from downstream processing, ensuring scalability, reliability, and performance.

## Architecture

<img width="729" height="456" alt="architecture-v1 drawio" src="https://github.com/user-attachments/assets/e4481860-8229-4916-8851-9e0660f60144" />



## Tech Stack

Backend:
- NestJS
- GraphQL (Apollo)
- Kafka
- Redis
- PostgreSQL

Frontend:
- Next.js 14

Infrastructure:
- Docker & Docker Compose

## Design Philosophy

This project follows an event-driven architecture to decouple activity ingestion from downstream processing. 

Instead of generating notifications synchronously within the request cycle, activity events are published to Kafka and processed asynchronously. This improves API responsiveness and enables horizontal scalability.

Redis is used as a caching layer to reduce repeated database reads for notifications and feed retrieval, improving latency and lowering database load.

PostgreSQL was chosen as the primary datastore due to the relational nature of the domain entities (users, activities, notifications) and the need for strong consistency and transactional guarantees.

The system is structured as a modular monolith with clear domain boundaries, allowing future extraction into microservices if scaling requirements demand it.

