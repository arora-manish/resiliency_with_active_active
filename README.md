# Introduction
Information systems are the backbone of organizational success, but they are exposed to a variety of disruptions, ranging from minor issues like short-term power outages, network failures, and disk malfunctions to more critical events such as equipment destruction, fires, or severed fiber connections. To bolster their resiliency, organizations can implement a combination of management, operational, and technical controls.

High-impact information systems demand meticulous consideration of high-availability and redundancy options during their design phase. These options might encompass the deployment of fully redundant load-balanced systems across alternate sites, data mirroring mechanisms, and the replication of databases to offsite locations. However, it's essential to acknowledge that high-availability solutions come at a considerable cost in terms of setup, operation, and maintenance, making them a viable choice primarily for mission-critical high-impact systems. Conversely, lower-impact information systems might opt for more cost-effective contingency measures while tolerating longer recovery times. 

# Geo distributed / Active – Active solutions overview
Geo-distributed/Active-Active technology platforms offer organizations the ability to minimize the impact of disruptions, enabling swift and effective recovery following a service disruption. Building a solution that remains functional despite system component failures requires meticulous planning across all levels of the architecture.

Resiliency can be achieved through well-defined patterns that touch every aspect of the solution, including infrastructure design, application architecture, storage choices, and deployment processes.

To achieve an uptime of 99.999% or higher (equivalent to just a few minutes of downtime per year), customers strategically deploy services across multiple instances, availability zones, and multi-regions. This approach ensures that even during a network partitioning event, the quality of service remains unaffected in each region.

To validate the resiliency of the system, various scenarios are considered, such as availability zone outages, split-brain incidents (loss of connectivity between regions), and event-driven traffic shifts between regions. Monitoring errors and responses during these scenarios is crucial to ensure the effectiveness of the resiliency measures.

This document aims to outline the technical considerations adopted by Redis's customers to implement preventive measures and recovery strategies, addressing their information system's resilience needs.

Key considerations for building a resilient architecture include:

Embracing a loosely coupled, independent component approach to enhance flexibility and resiliency.
Designing services to be stateless and accessing resources locally within their respective regions.
Avoiding cross-regional calls whenever feasible.
Implementing asynchronous data replication in the data tier to ensure data consistency and redundancy.

By following these technical considerations, organizations can bolster the resiliency of their systems and better prepare for potential disruptions.

# resiliency_with_active_active
These diagrams aims to outline the technical considerations adopted by Redis's customers to implement preventive measures and recovery strategies, addressing their information system's resilience needs.
