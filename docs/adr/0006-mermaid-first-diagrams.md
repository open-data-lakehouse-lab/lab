# ADR 0006: Mermaid-First Diagrams

## Status

Accepted

## Context

We need a way to include diagrams in our documentation that is version-control friendly and easy to maintain.

## Decision

We will use Mermaid for all diagrams in the project. Mermaid allows for text-based diagram definition which can be rendered directly by GitHub and other tools.

ASCII diagrams or binary image formats (PNG, JPG) for diagrams should be avoided where Mermaid can be used.

## Consequences

- Diagrams are easily editable and versionable.
- Consistency across all documentation.
- No need for external proprietary diagramming tools.
