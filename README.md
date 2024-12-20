# FastAPI MS Boiler-Plate

This repository offers boilerplate code for initiating a [Dockerized](https://www.docker.com/)  [FastAPI](https://fastapi.tiangolo.com/)-[PostgreSQL](https://www.postgresql.org/?&)-[SQLAlchemy](https://www.sqlalchemy.org/)-[Alembic](https://alembic.sqlalchemy.org/en/latest/) project. It includes a [pre-commit](https://pre-commit.com/) framework configured with [mypy](https://mypy.readthedocs.io/en/stable/index.html) and [ruff](https://beta.ruff.rs/docs/) to ensure consistent code formatting and strict typing. Whether you're building microservices or a larger application, this template streamlines your project setup, allowing you to focus on developing your FastAPI-based microservices with confidence

Use this template as a starting point to quickly set up a robust and scalable FastAPI project with PostgreSQL, taking advantage of powerful features like automatic API documentation generation, asynchronous capabilities, and containerization for easy deployment.

### Required


## Table of Contents
- [Features](#features)
- [Usage](#usage)
- [Environment Variables](#environment-variables)

---


## Features
- FastAPI framework for building high-performance APIs
- PostgreSQL database integration with SQLAlchemy for efficient data management
- Alembic for seamless database schema migrations
- Pre-commit framework with MyPy and ruff for code formatting and strict typing checks
- CRUD base class fot instance with needed model
- Project config file fo ease update configurations
- Utils function in utils.py (client and consumer for RabbitMQ broker for example)


Get started with your FastAPI project in no time using this template repository!


## Usage
**Initial Setup**

- Init project:
    - create and activate a [virtual env](https://docs.python.org/3/library/venv.html#module-venv)
    - install initial dependencies
    - install pre-commit config and run in all file to initial check
Positioning in the project root run make the following make command:
```sh
    make init
```
## Environment Variables
**Local Development**

To set up environment variables for local development, follow these steps:

1. Create a `.env` file in the root directory of your project.
2. Add the necessary environment variables to the .env file in the format KEY=VALUE. Adjust the [config.py](config.py) file to insert these variables into the config class instance.

Example .env file:
```txt
DB_HOST=localhost
DB_PORT=5432
DB_USER=myuser
DB_PASSWORD=mypassword
```

**Before to deploy**

To set up environment variables for deployment, follow these steps:

1. Create into github an environment called `Development`
2. Add to your environment variables the `ECS_SERVICE` variable with the name of the service in ECS
3. Note: For each environment you need to create a new environment in github and add the `ECS_SERVICE` variable with the name of the service in ECS, example

| Environment | ECS_SERVICE |
| ----------- | ----------- |
| Development | trx-service-name-dev  |
| Staging     | trx-service-name-stg  |
| Production  | trx-service-name |