# Project Structure

The **Python** api uses the FastAPI framework.

## **Directories**

:fontawesome-solid-hand-point-right:{ .main } The `main.py` file in `/app` contains the app initialization and middleware logic.

:fontawesome-solid-hand-point-right:{ .main } The `database` directory contains the database model definitions in `models.py`, the `sqlalchemy` initialization logic in `db.py`. All the database queries are spread across multiple files (named after the corresponding functionality) in the `data_access` sub-directory.

:fontawesome-solid-hand-point-right:{ .main } `routers` contains all the REST endpoints called from the website.

:fontawesome-solid-hand-point-right:{ .main } `helpers` contains some helper functions like the initialization methods for third party services.
