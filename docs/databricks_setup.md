# Get access to Databricks

## Your starting point

You selected Databricks and need help getting a workspace. For this personal portfolio and learning project, the recommended starting route is **Databricks Free Edition**. It provides a no-cost learning workspace with serverless compute and default storage. See the [official signup guide](https://docs.databricks.com/aws/en/getting-started/free-edition).

This is a recommendation and access guide. No account has been created or workspace access verified by the repository scaffold.

## Signup steps

1. Open the [Databricks Free Edition page](https://www.databricks.com/learn/free-edition) and select **Sign up for Free Edition**.
2. Choose the available Google, Microsoft, or personal email signup method and complete the sign-in prompts yourself.
3. Follow the prompts to enter the workspace Databricks creates for you.
4. Bookmark your workspace address. Reaching the workspace home page is the access checkpoint for this phase; no tables or pipeline code need to be created yet.

The signup process and automatic workspace creation are described in [Databricks documentation](https://docs.databricks.com/aws/en/getting-started/free-edition). The available email and social sign-in methods are listed under [Free Edition authentication](https://docs.databricks.com/aws/en/getting-started/free-edition-limitations).

Free Edition is the personal-use offering. The broader signup site also offers a time-limited business trial; use the option labeled Free Edition for this learning route. Databricks' [signup comparison](https://www.databricks.com/try-databricks) states that Free Edition requires no cloud account or payment.

## What this means for our later lessons

Free Edition uses serverless compute and has fair-use quotas and restricted internet access. We will keep datasets small and check supported features before implementing each phase. See [Free Edition limits](https://docs.databricks.com/aws/en/getting-started/free-edition-limitations).

Serverless compute uses Spark Connect APIs, and DataFrame caching APIs are unavailable in the current documented environment. We can learn the supported DataFrame and SQL operations there; hands-on caching demonstrations may require another environment later. We will discuss that trade-off when the lesson needs it rather than installing a second stack now. See [serverless API and caching limits](https://docs.databricks.com/aws/en/compute/serverless/limitations).

Before Phase 2, we will confirm workspace access, the available environment, and an appropriate location for source files and Delta tables. The managed environment supplies Spark and Delta capabilities. No local PySpark, Delta Lake, Databricks CLI, or MLflow installation is required by Phase 0.
