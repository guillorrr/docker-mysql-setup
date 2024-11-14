# Project Setup

## Recommended Setup
This setup is ideal for launching an SQL database with a database dump.

### Project Structure

Your project should follow this structure:

```
. 
├── dump.sql.gz
├── docker-compose.yml 
└── README.md
```

- **`dump.sql.gz`**: Database dump file for initializing the database.
- **`docker-compose.yml`**: Docker Compose file for configuring and running the project.
- **`README.md`**: Project documentation.

## Steps

1. Copy `.env.example` to `.env`:
   ```bash
   cp .env.example .env
   ```

2. Modify the default values in .env as needed.

## Running the Project

### To start the project with verbose:
```bash
docker compose up
```

### To start in detached mode:

```bash
docker compose up -d
```

### Database Import

The SQL import will only run the first time the project starts, if the database is empty. If data exists, remove the volume with:

```bash
docker compose down -v
```

## Accessing the Application

To access phpMyAdmin, go to http://localhost:8082. Use the credentials from .env (DB_USER and DB_ROOT_PASSWORD).