# snowflake-dbt-assessment

dbt project for Maids.cc assessment using Snowflake TPCH sample data on Snowflake.

## Prereqs
- Python 3.9+
- `pip install dbt-snowflake`
- Snowflake trial with:
  - Role: `ACCOUNTADMIN`
  - Warehouse: `DEV_WH`
  - Database: `DEV_DB`
  - Schema: `DEV`

## Configure dbt profile
Create `~/.dbt/profiles.yml`:

```yaml
snowflake_tpch_demo:
  target: dev
  outputs:
    dev:
      type: snowflake
      account: <your-account>          # e.g. jp66911.af-south-1.aws
      user: <your-username>
      password: <your-password>
      role: ACCOUNTADMIN
      database: DEV_DB
      warehouse: DEV_WH
      schema: DEV
      threads: 4
