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
4. **Transformation**: Converting landing JSON to bronze JSONL.
5. **Quality (Bronze)**: Validating bronze JSONL files.
6. **Orchestration**: Running the flow and generating a `run-summary.json`.
7. **Observability**: Generating Markdown and JSON reports based on the run summary and quality results.
8. **Dashboards**: Generating a static HTML dashboard to visualize pipeline execution and observability metrics.

## Supported Dataset

- **Name**: `meteocat-weather` (Servei Meteorològic de Catalunya)
- **Supported Resources**:
  - `stations-metadata`
  - `variables-metadata`
  - `measured-variable`

## Artifact Types

- **Landing**: JSON
- **Bronze**: JSONL
- **Observability**: JSON and Markdown reports
- **Dashboards**: Static HTML

## Local E2E validation

The local Weather MVP vertical slice has been executed successfully.

- The run used sample/offline ingestion mode.
- The run did not require cloud credentials.
- The run did not require external services.
- The verified steps were:
    - ingestion
    - landing quality
    - transformation
    - bronze quality
- Observability report generation and static dashboard rendering were successfully executed after the orchestration run.
- Generated artifacts are reproducible and should not be committed.

### Verified artifact paths (relative)

```text
orchestration/workspace/runs/<run-id>/landing/landing/weather/meteocat/meteocat-weather/ingestion_date=<date>/sample.json
orchestration/workspace/runs/<run-id>/bronze/bronze/weather/meteocat/stations-metadata/processing_date=<date>/records.jsonl
orchestration/workspace/runs/<run-id>/reports/run-summary.json
orchestration/workspace/observability/run-observability-report.json
orchestration/workspace/observability/run-observability-report.md
orchestration/workspace/dashboard/index.html
```

## Current Limitations

- **Not production-ready**: Intended for laboratory and development purposes.
- **No real cloud deployment**: Currently restricted to local execution.
- **No Silver/Gold modeling**: Only Landing and Bronze layers are implemented.
- **No local cloud emulator integration**: Integration with local cloud emulator candidates is not yet part of the main flow.
- **No external observability stack**: Reports are currently local files.
- **No advanced BI tool**: Dashboards are static HTML.

## Next Steps

- Hardening real API execution.
- Implementing schema verification.
- Designing and implementing Silver and Gold modeling layers.
- Integrating local cloud emulators into the flow.
- Automated end-to-end CI/CD.
