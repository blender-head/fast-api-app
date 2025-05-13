# fast-api-app

## Course Source:
[Sanjeev-Thiyagarajan](https://github.com/Sanjeev-Thiyagarajan/fastapi-course/tree/main)

## Using Alembic

Alembic is a lightweight database migration tool for SQLAlchemy. Here's how to run migrations with Alembic

### Initial Setup
1. Install Alembic:
```
pip install alembic
```

2. Initialize Alembic in your project:

```
alembic init alembic
```

This creates an alembic directory with configuration files.

3. Modify `alembic\env.py`

Connect alembic to the database

```
config.set_main_option(
    "sqlalchemy.url", 
    f"mysql+mysqldb://{settings.database_username}:{settings.database_password}@{settings.database_hostname}:{settings.database_port}/{settings.database_name}"
)
```