# dbt-snowflake-netflix-elt-pipeline
End-to-End Netflix Data Pipeline with dbt, Snowflake

Built a modern ELT pipeline to transform raw Netflix ratings and movie metadata into analytics-ready models using dbt (Data Build Tool), following software engineering best practices (modular SQL, version control, testing).

• Ingested large Netflix/MovieLens CSV datasets into Snowflake from cloud storage, set up staging schemas, and defined dbt sources to enable reliable transformation workflows.

• Developed dbt models including fact and dimension tables (e.g., fct_ratings) to organize user ratings, movie details, and related metrics for downstream analytics and reporting. (The fct_ratings model consolidates rating events into a fact table linking users, movies, rating scores, and timestamps).

• Implemented dbt materializations (views/tables) to balance performance and storage needs, and configured model dependencies using ref() for maintainable SQL transformations.

• Applied dbt tests (generic tests such as not_null, unique) to ensure data quality for critical fields in fact and dimension models.

• Generated dbt documentation and model lineage graphs, improving transparency and team collaboration on data logic definitions.

Stack / Tools

dbt, Snowflake, AWS S3 (or equivalent cloud staging), SQL

<img width="1142" height="546" alt="image" src="https://github.com/user-attachments/assets/9491cb59-d61c-41d4-8652-167469ebcd02" />

Key Deliverables

Staged raw Netflix datasets into Snowflake

Project: Netflix Data Analysis (dbt + Snowflake)

Goal: Build a production-style ELT pipeline that turns raw MovieLens files into analytics-ready tables and dashboards.

Tech Stack: Amazon S3, Snowflake, dbt, Looker Studio / Power BI

Architecture:

Extract: stage CSVs in S3

Load: ingest raw tables into Snowflake

Transform: build modular dbt models + tests + docs

Serve: connect curated tables to BI dashboards

Data Modeling (dbt):

Staging models: standardize raw schemas and types

Core models: build reusable dimensions and a ratings fact layer (example: fct_ratings)

Quality: dbt tests + optional custom checks

Governance: auto-generated docs + DAG lineage

<img width="1097" height="536" alt="image" src="https://github.com/user-attachments/assets/e9d40ada-9939-4ed5-b73e-703811aaa3d6" />


How to run (example):

Configure Snowflake profile + dbt project connection

dbt deps

dbt build (models + tests)

dbt docs generate and dbt docs serve

Implemented dbt best practices: modular models, dependency management with ref(), materializations, and documentation with lineage (DAG) for maintainable analytics engineering workflows.

Modeled Netflix-style analytics using the MovieLens 20M dataset, transforming raw CSVs into clean, analytics-ready tables for reporting.

Built a ratings fact model (fct_ratings) as part of the curated layer to support metrics like rating distribution, content popularity, and user activity patterns.

Added data quality coverage using dbt generic tests like unique, not_null, accepted_values (and custom tests where needed) to catch bad loads and modeling regressions early.

Used dbt features like seeds (static lookup/reference data), snapshots (SCD Type 2 history tracking), and macros (reusable Jinja logic) to make the project production-like

dbt models: staging, dimensions (e.g., users, movies), facts (e.g., ratings)

Data quality tests and documentation

Dashboards visualizing rating trends and user engagement
