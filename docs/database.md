# The database

The project uses a self hosted **PostgreSQL** database that runs on the same server as the website and the backend api.

All calls to the database are made by the **Python** api using the SQLAlchemy library. The api uses the async flavor of the SQLAlchemy ORM for the DDL and DML logic.

Developers are required to download PostgreSQL 12 or higher for local development. As an add-on, developers can also download a tool like PgAdmin (or equivalent) to easily work with the data.

When developing locally, assuming the developer is using the default PostgreSQL values, the connecting string for the database in the `.env` file, in the `api` project will look something like this -

`SQLALCHEMY_DATABASE_URI=postgresql+asyncpg://postgres:postgres@127.0.0.1:5432/mes-aa`

`mes-aa` here is the name of the database.

## **Models**

The **Python** api contains all the model definitions in `/database.models.py`.

## **Migrations**

For database migrations, the project uses the Alembic library. Migrations need to be run separately on the server during deployment.
