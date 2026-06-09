# M1 - Weather Local Vertical Slice

This document describes the implementation of the first local vertical slice for the Open Data Lakehouse Lab, focusing on weather data.

## Goal

To implement a complete end-to-end data flow from source selection to visualization, running entirely in a local environment without cloud dependencies.

## Implemented Repositories

- `datasets-catalog`
- `ingestion`
- `transformation`
- `quality`
- `orchestration`
- `observability`
- `dashboards`
- `open-data-lakehouse-lab.github.io`

## Current Flow

1. **Dataset Catalog**: Selection of `meteocat-weather` dataset.
2. **Ingestion**: Fetching data from source and saving it as landing JSON.
3. **Quality (Landing)**: Validating landing JSON files.
4. **Transformation (Bronze)**: Converting landing JSON to bronze JSONL.
5. **Quality (Bronze)**: Validating bronze JSONL files.
6. **Transformation (Silver)**: Converting bronze JSONL to silver JSONL foundation.
7. **Quality (Silver)**: Validating silver JSONL files.
8. **Orchestration**: Running the flow and generating a `run-summary.json`.
9. **Observability**: Generating Markdown and JSON reports based on the run summary and quality results.
10. **Dashboards**: Generating a static HTML dashboard to visualize pipeline execution and observability metrics.

## Supported Dataset

- **Name**: `meteocat-weather` (Servei Meteorològic de Catalunya)
- **Supported Resources**:
  - `stations-metadata`
  - `variables-metadata`
  - `measured-variable`

## Artifact Types

- **Landing**: JSON
- **Bronze**: JSONL
- **Silver**: JSONL
- **Observability**: JSON and Markdown reports
- **Dashboards**: Static HTML

## Local E2E validation

The local Weather MVP vertical slice has been executed successfully in multi-resource mode with Silver included.

The run has been verified both without contracts and with optional landing contract validation.

- Verified command modes:
    - `--resource all`
    - `--resource all --use-contracts`
- The run used sample/offline ingestion mode.
- The run did not require cloud credentials.
- The run did not require external services.
- The verified resources were:
  - `stations-metadata`
  - `variables-metadata`
  - `measured-variable`
- The verified Silver mappings were:
  - `stations-metadata -> stations`
  - `variables-metadata -> variables`
  - `measured-variable -> measurements`
- The verified orchestration steps were executed for each resource:
  - ingestion
  - quality-landing
  - transformation
  - quality-bronze
  - transformation-silver
  - quality-silver
- When `--use-contracts` is enabled, `quality-landing` validates landing JSON against the draft internal contracts and permissive schemas from `datasets-catalog`.
- Contract validation is opt-in.
- Default orchestration behavior remains unchanged.
- Observability report generation and static dashboard rendering were successfully executed after the orchestration run.
- Generated artifacts are reproducible and should not be committed.
- The Silver layer is still a local foundation, not a final analytics model.

### Verified artifact paths (relative)

```text
orchestration/workspace/runs/<run-id>/landing/landing/weather/meteocat/meteocat-weather/ingestion_date=<date>/sample.json
orchestration/workspace/runs/<run-id>/bronze/bronze/weather/meteocat/stations-metadata/processing_date=<date>/records.jsonl
orchestration/workspace/runs/<run-id>/bronze/bronze/weather/meteocat/variables-metadata/processing_date=<date>/records.jsonl
orchestration/workspace/runs/<run-id>/bronze/bronze/weather/meteocat/measured-variable/processing_date=<date>/records.jsonl
orchestration/workspace/runs/<run-id>/silver/silver/weather/meteocat/stations/processing_date=<date>/records.jsonl
orchestration/workspace/runs/<run-id>/silver/silver/weather/meteocat/variables/processing_date=<date>/records.jsonl
orchestration/workspace/runs/<run-id>/silver/silver/weather/meteocat/measurements/processing_date=<date>/records.jsonl
orchestration/workspace/runs/<run-id>/reports/run-summary.json
orchestration/workspace/observability/run-observability-report.json
orchestration/workspace/observability/run-observability-report.md
orchestration/workspace/dashboard/index.html
```

## Current Limitations

- **Not production-ready**: Intended for laboratory and development purposes.
- **No real cloud deployment**: Currently restricted to local execution.
- **No Gold modeling**: Only Landing, Bronze and Silver foundation layers are implemented.
- **No local cloud emulator integration**: Integration with local cloud emulator candidates is not yet part of the main flow.
- **No external observability stack**: Reports are currently local files.
- **No advanced BI tool**: Dashboards are static HTML.

## Next Steps

- Hardening real API execution.
- Implementing schema verification.
- Designing and implementing Gold modeling layers.
- Integrating local cloud emulators into the flow.
- Automated end-to-end CI/CD.
