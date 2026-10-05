# 0001: Establish the Phase 0 foundation

Date: 2026-10-05

Status: Foundation follows the user-provided brief. The learner selected Databricks and needs help getting access. Workspace access, runtime details, and pipeline decisions remain open.

## Context

This project is both a portfolio and a mentored learning exercise. Generating all layers immediately would skip the learner's reasoning about source contracts, data quality, modeling, and reliable processing.

The brief specifies a Databricks-oriented medallion platform using Python, SQL, PySpark, Spark, Delta Lake, Workflows, and eventually MLflow. Phase 0 is limited to explanations, documentation, and repository setup.

## Foundation choices

1. Preserve the requested repository layout. It separates source data, future reusable code, notebooks, tests, configuration, and documentation without introducing a framework or deployment system.
2. Treat Raw, Bronze, Silver, and Gold as separate responsibilities in the target design. This supports tracing and replay, at the cost of more copies and steps. Actual schemas and storage locations are not selected here.
3. Use placeholders rather than implement later-phase code. Git retains files rather than empty directories, so `.gitkeep` records the reserved folders.
4. Require no third-party Python packages in Phase 0. Runtime-dependent versions will be selected together before Spark execution; test tooling will accompany real tests.
5. Ignore generated raw data and local runtime state. Later reproducibility will come from generation code, documented configuration, and small reviewed synthetic samples.
6. Record open decisions rather than silently solve them for the learner. Major choices will follow explanation, learner attempt, review, and implementation.

## Alternatives and consequences

A single notebook would be faster to start but would mix responsibilities and make reusable logic harder to test. Separate module folders prepare for reviewable increments; packaging will be chosen when code exists.

Installing the complete target stack now would make the environment larger before any code uses it and could conflict with a later managed runtime. Deferring those packages keeps setup tied to actual execution requirements.

The medallion target is given by the brief. Other storage and transformation designs are not ruled out in general; their relevance will be discussed when a concrete requirement warrants comparison.

## Open decisions

- Databricks workspace access and available runtime features. Free Edition is the recommended starting route; account creation has not been verified. See [the access guide](../databricks_setup.md).
- Source formats, initial size, seed/configuration for repeatable generation, and money/time conventions.
- Ingestion schema handling, metadata, and replay behavior.
- Cleaning, deduplication, quarantine, and business validation rules.
- Gold table grains, keys, and metric definitions.
- Incremental processing, orchestration, and performance choices.

This record documents the authorized foundation. It does not claim that future pipelines are implemented, tested, or reliable.
