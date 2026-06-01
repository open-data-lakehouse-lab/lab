# ADR 0004: Azure-First MVP

## Status

Accepted

## Context

While the vision is multi-cloud, we need a starting point for the MVP to avoid over-engineering and to deliver value quickly.

## Decision

The MVP will focus on an Azure-oriented local lab environment. This means we will prioritize tools and patterns that are common or easily translatable to Azure services, while keeping them local-friendly (e.g., using Azurite for storage simulation).

## Consequences

- Faster initial delivery.
- Clearer focus for the first few milestones.
- Patterns established here will be replicated to AWS and GCP in later milestones.
