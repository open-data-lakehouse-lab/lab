# Architecture Overview

The Open Data Lakehouse Lab follows a modular architecture based on open standards and a multi-cloud strategy.

## High-Level Data Flow

```mermaid
flowchart LR
    ODS[Open Data Sources] --> Ingestion[Ingestion]
    Ingestion --> Landing[Landing / Raw]
    Landing --> Bronze[Bronze]
    Bronze --> Silver[Silver]
    Silver --> Gold[Gold]
    Gold --> Dashboards[Dashboards]
    Gold --> API[Analytics API]
    Gold --> Web[Web Portal]
    Gold --> Docs[Public Documentation]
```

## Architecture Principles

- **Multi-cloud**: Neutrality across cloud providers (Azure, AWS, GCP).
- **Open Standards**: Use of open data formats and protocols.
- **Local-First**: Ability to run the laboratory in a local environment.
- **Data Lakehouse**: Combining the best of data lakes and data warehouses.
