# ADR 0003: Multi-Repository Architecture

## Status

Accepted

## Context

A single repository might become too large and hard to manage given the different components of a data lakehouse (infrastructure, ingestion, transformation, etc.).

## Decision

We will use a multi-repository architecture. Each major component or service will have its own dedicated repository under the `open-data-lakehouse-lab` organization.

The `lab` repository will serve as the central governance and coordination point.

## Consequences

- Improved modularity and separation of concerns.
- Ability to use different tech stacks for different components.
- Easier to manage permissions and CI/CD pipelines.
- Requires a central map to navigate the repositories.
