# Phase 0 learning checkpoint

## What was prepared

- An initial README with the business problem, target architecture, and phased roadmap.
- An architecture guide explaining layer responsibilities and technology differences.
- A Databricks access guide tailored to your need for a new workspace.
- A source outline preserving the requested entities without finalizing later models.
- Reserved folders for source data, reusable code, notebooks, tests, configuration, and scripts.
- Git ignore rules for local environments, credentials, generated data, and runtime state.
- A comments-only requirements file because this phase needs no third-party libraries.
- A foundation decision record explaining scope and choices still to make.

There are no generated datasets, runnable pipelines, deployed workflows, dashboards, or trained models. Folder names are placeholders for work in later phases.

## What you should understand

You should be able to trace source data through Raw, Bronze, Silver, and Gold, and explain how each step increases its usefulness. Preserving input provides evidence for debugging and replay; cleaning establishes trust; business modeling gives reporting a shared meaning.

You should distinguish languages and interfaces from engines, storage, and orchestration:

- Python and SQL express logic.
- PySpark is the Python API for Spark.
- Spark executes data processing.
- Parquet is a column-oriented file format; Delta adds a transaction log and table capabilities.
- Databricks provides a managed platform for running workloads.
- Workflows / Lakeflow Jobs coordinates tasks, while Spark executes computations inside them.
- MLflow records ML experiments and models in the later ML phase.

The detailed explanations and official references are in [architecture.md](architecture.md).

You should also recognize the engineering purpose of the repository layout: reusable modules support tests and reuse, notebooks support inspection, configuration keeps environment-specific settings separate, and documentation records reasoning.

You are not expected to master Spark shuffles, Delta merges, dimensional models, or deployment during Phase 0. Those need concrete examples in their later phases.

## Five short understanding questions

Answer in your own words; one to three sentences per answer is enough.

1. Why preserve an order's original source values in Bronze before cleaning them in Silver?
2. How do Spark and PySpark differ, and where does Python fit?
3. What does Delta Lake add to Parquet files, and does it automatically remove duplicate records?
4. How do Databricks and Databricks Workflows differ from the Spark engine?
5. Which layer should define a daily sales metric, and why separate that definition from cleaning orders?

## Before Phase 1

Review your answers with your mentor and correct any misunderstandings first. Then propose a source file format and a way to make generated datasets reproducible. We will discuss the alternatives and agree the first realistic quality problem before generating data.

The mentor should explain major decisions, ask for your approach, let you attempt the reasoning or implementation, and review the result. Boilerplate can be implemented directly. Summarize the completed phase before moving to a major new phase.
