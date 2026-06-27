# ResultGrid Load Testing & Performance Validation

## Purpose

ResultGrid is designed to support high-read workloads during university examination result publication periods, where thousands of users attempt to access immutable result data simultaneously.

The objective of this document is to define measurable performance goals, testing methodology, system metrics, and future validation results.

---

# Target Workload

Prototype Dataset

* Districts: 3
* Colleges per District: 10
* Departments per College: 5
* Academic Years: 4
* Students per Academic Year: 30

Total Student Records

18,000+

Expected Usage Pattern

* Read-heavy workload
* Burst traffic
* Concurrent client requests
* Immutable result data
* Low write frequency

---

# Performance Goals

Primary Goal

Support approximately **18,000 concurrent client requests** while maintaining reliable response times and minimizing database contention.

Secondary Goals

* Reduce repeated database access using local caching.
* Maintain predictable API latency under increasing load.
* Observe backend resource utilization.
* Validate scalability before introducing distributed components.

---

# Testing Stages

## Stage 1

Concurrent Clients

100

Purpose

Verify correctness.

Metrics

* Average response time
* Error rate
* CPU usage
* Memory usage

Status

Planned

---

## Stage 2

Concurrent Clients

1,000

Purpose

Observe cache behaviour and connection pool utilization.

Metrics

* p50 latency
* p95 latency
* Throughput (requests/sec)
* Active database connections
* Cache hit ratio

Status

Planned

---

## Stage 3

Concurrent Clients

5,000

Purpose

Evaluate scalability under sustained concurrent traffic.

Metrics

* Throughput
* Average latency
* Peak memory
* CPU utilization
* Database query count

Status

Planned

---

## Stage 4

Concurrent Clients

18,000

Purpose

Validate architectural target.

Metrics

* p50 latency
* p95 latency
* p99 latency
* Requests/sec
* Cache hit ratio
* Active HikariCP connections
* Error percentage
* Maximum heap usage
* Database query count
* Spring Boot Actuator metrics

Status

Planned

---

# Cache Validation

Technology

Caffeine Local Cache

Measurements

* Cache hit ratio
* Cache miss ratio
* Average lookup latency
* Database queries prevented
* Memory footprint

---

# Database Validation

Database

PostgreSQL

Measurements

* Register Number lookup latency
* Indexed query performance
* EXPLAIN ANALYZE output
* Connection pool utilization
* Query execution time

---

# Observability

Spring Boot Actuator

Metrics

* HTTP request statistics
* JVM memory usage
* CPU utilization
* Active threads
* Request throughput
* Error rate
* Health endpoint
* Cache statistics

---

# Future Resume Metrics

The following measurements are intended for future resume updates after implementation.

Example

* Validated support for approximately 18,000 concurrent client requests.
* Achieved p95 latency below ______ ms.
* Sustained ______ requests/sec.
* Reduced database queries by ______% through local caching.
* Achieved cache hit ratio of ______%.
* Maintained application error rate below ______%.

---

# Current Status

Architecture Design

✅ Completed

Backend Skeleton

✅ Completed

Caching Strategy

In Progress

Load Testing

Planned

Performance Validation

Pending

Resume Quantification

Pending after benchmarking
