# Astronomer Project

This project was initialized using the Astronomer CLI's `astro dev init` command. It provides a local Apache Airflow development environment.

## Project Structure

- `dags/` - Contains your Airflow DAGs
  - `example_astronauts` - Example DAG demonstrating ETL pipeline using TaskFlow API and dynamic task mapping to process astronaut data from Open Notify API
- `Dockerfile` - Contains versioned Astro Runtime Docker image and runtime commands
- `include/` - Additional project files
- `packages.txt` - OS-level package dependencies
- `requirements.txt` - Python package dependencies
- `plugins/` - Custom and community Airflow plugins
- `airflow_settings.yaml` - Local configuration for Airflow Connections, Variables, and Pools

## Local Development

1. Start Airflow locally:
```bash
astro dev start
```

This creates four Docker containers:
- Postgres (Metadata Database)
- Webserver (UI)
- Scheduler (Task monitoring and triggering)
- Triggerer (Deferred task handling)

2. Verify containers are running:
```bash
docker ps
```

3. Access Airflow:
- UI: http://localhost:8080
- Default credentials: admin/admin
- Postgres: localhost:5432/postgres

Note: If ports 8080 or 5432 are already in use, either stop existing containers or modify the ports according to [Astronomer's documentation](https://www.astronomer.io/docs/astro/cli/troubleshoot-locally#ports-are-not-available-for-my-local-airflow-webserver).

## Deployment

For instructions on deploying to Astronomer's cloud platform, visit: https://www.astronomer.io/docs/astro/deploy-code/

