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

### Running Migrations

1. Create a new migration

```
alembic revision -m "your migration message"
```

This creates a new migration file in alembic/versions/ that you need to edit with your schema changes.
2. Run migrations to upgrade

```
alembic upgrade head
```

This applies all pending migrations to bring your database to the latest version.

3. Run migrations to downgrade

```
alembic downgrade -1
```

This rolls back the last migration. You can also specify a specific revision ID.