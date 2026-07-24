Welcome to your new dbt project!

### Using the starter project

Try running the following commands:
- dbt run
- dbt test


### Resources:
- Learn more about dbt [in the docs](https://docs.getdbt.com/docs/introduction)
- Check out [Discourse](https://discourse.getdbt.com/) for commonly asked questions and answers
- Join the [chat](https://community.getdbt.com/) on Slack for live discussions and support
- Find [dbt events](https://events.getdbt.com) near you
- Check out [the blog](https://blog.getdbt.com/) for the latest news on dbt's development and best practices

# What is Sources.yml
- sources.yml is a YAML file under the models/ directory that tells dbt:
    These tables already exist in the warehouse - dbt does NOT build them, but I want to reference, test, and document them.
- Without sources:
    - Raw tables are just hard-coded strings
    - No freshness checks
    - No upstream visibility in dbt docs
- With sources:
    - Centralized table definitions
    - Built-in data quality tests
    - Freshness monitoring
    - Clear lineage (raw -> staging -> marts)

## Key purpose of dbt sources
- Explicitly declare raw data
    - You define where raw data lives (scheam + table) in YAML.
- Enable data freshness checks
    - dbt can warn you if upstream data is stale.
- Improve lineage & documentation
    - Sources appear in dbt docs
    - DAG / lineage graphs
- Safer refactoring
    - If schema or table names change, you update YAML, not every SQL file.
