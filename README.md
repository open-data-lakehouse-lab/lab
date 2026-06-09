# Open Data Lakehouse Lab

Open Data Lakehouse Lab is a personal open-source laboratory for building a multi-cloud open data lakehouse with public datasets, local cloud-like environments, Infrastructure as Code, data pipelines, analytics services and dashboards.

The project is independent, neutral, and uses only public open datasets.

## Vision

To provide a reproducible, technology-agnostic reference architecture for a modern data lakehouse using open-source tools and public data.

## Project Structure

This repository (`lab`) is the central governance repository. It acts as the project control plane and contains:

- [Global vision](README.md)
- [Roadmap](ROADMAP.md)
- [Repository map](REPOSITORIES.md)
- [Architecture overview](ARCHITECTURE.md)
- [Project principles](docs/governance/project-principles.md)
- [Current status](docs/governance/current-status.md)
- [Architecture Decision Records (ADRs)](docs/adr/)
- [Contribution guidelines](CONTRIBUTING.md)

## Current Status

The project has implemented its first **local Weather MVP vertical slice**.

- **Selected Dataset**: `meteocat-weather` (Public weather data from Catalonia).
- **Core Local Flow**:
  - Dataset catalog selection.
  - Landing JSON ingestion (Sample mode by default, hardened opt-in real API mode).
  - Landing quality checks.
  - Bronze JSONL transformation.
  - Bronze quality checks.
  - Orchestration run summary.
  - Observability reports (JSON and Markdown).
  - Static HTML dashboard.

The flow is **local-first** and does not require cloud credentials. It is currently intended for development and exploration and is **not production-ready**. Real cloud deployment and local cloud emulator integration are planned for future milestones.

## Getting Started

Refer to the [M0 - Foundation](docs/planning/m0-foundation.md) milestone to see the initial setup progress.

## License

Unless otherwise noted:

- Documentation, articles, diagrams, dataset metadata, data dictionaries, schemas, data contracts and written content are licensed under the [Creative Commons Attribution 4.0 International License](https://creativecommons.org/licenses/by/4.0/).
- Software, scripts, Infrastructure as Code, SQL models, configuration files and executable assets are licensed under the [Apache License 2.0](LICENSE-CODE).

Original upstream datasets, when referenced, remain governed by their original source licenses and terms.
