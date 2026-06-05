# ADR 0008: Local Weather MVP vertical slice

## Status

Accepted

## Context

The Open Data Lakehouse Lab aims to build a multi-cloud data lakehouse. To validate the core architecture and provide a tangible proof of concept, we need to implement a first vertical slice.

## Decision

We decided to implement the first MVP as a **local-first vertical slice** using lightweight, repository-specific CLIs and local artifacts.

Key decision points:
- **Local-first execution**: The flow must run without requiring cloud accounts or credentials.
- **Repository-specific CLIs**: Each repository provides its own CLI for its specific responsibility.
- **Landing Layer**: Uses JSON for raw data storage.
- **Bronze Layer**: Uses JSONL (JSON Lines) for initial structured storage.
- **Local quality checks**: Integrated validation of JSON and JSONL artifacts.
- **Subprocess-based orchestration**: Use of a simple orchestrator to manage the execution of different repository CLIs.
- **Local observability reports**: Generation of JSON and Markdown reports stored locally.
- **Static HTML dashboard**: Using lightweight static site generation for data visualization.

## Consequences

- **Speed of development**: We can iterate quickly without cloud latency or costs.
- **Independence**: The lab remains neutral and easy for anyone to run locally.
- **Portability**: The logic is decoupled from specific cloud services at this stage.
- **Technical Debt**: We will need to replace some local-specific parts (like local file paths) with cloud-agnostic abstractions in the future.

## Current implemented flow

1. **Dataset Catalog**: `meteocat-weather` selection.
2. **Ingestion**: `landing JSON` generation.
3. **Quality**: `JSON validation`.
4. **Transformation**: `bronze JSONL` generation.
5. **Quality**: `JSONL validation`.
6. **Orchestration**: `run-summary.json` generation.
7. **Observability**: `JSON and Markdown` reports.
8. **Dashboards**: `static HTML` generation.

## Non-goals for this ADR

- **Production readiness**: This is a laboratory MVP, not a production system.
- **Real cloud deployment**: Cloud-specific implementation is deferred to later milestones.
- **External orchestrator selection**: We are not yet choosing a final orchestrator (like Airflow or Dagster).
- **External observability stack selection**: We are not yet choosing a final observability platform (like Grafana or Datadog).
- **Advanced BI tool selection**: We are using static HTML for now instead of complex BI tools.
- **Silver/Gold final modeling**: Modeling beyond the Bronze layer is out of scope for this initial slice.

## Future work

- Integration with local cloud emulator candidates.
- Evaluation of Parquet for Silver/Gold layers.
- Transitioning to cloud storage (S3, ADLS, GCS).
