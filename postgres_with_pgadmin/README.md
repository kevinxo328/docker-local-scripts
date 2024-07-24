# PostgreSQL and pgAdmin Docker Compose Setup

## Overview

This Docker Compose file provides a quick setup for running PostgreSQL and pgAdmin. With this configuration, you can easily set up and run a PostgreSQL database and the pgAdmin web interface on your local machine.

## Components

1. **PostgreSQL**: A powerful open-source relational database management system.
2. **pgAdmin**: A web-based management interface for PostgreSQL, providing a graphical interface for managing and interacting with PostgreSQL databases.

## Configuration

### PostgreSQL

- **Image**: `postgres:latest`
- **Environment Variables**:
  - `POSTGRES_PASSWORD`: Sets the PostgreSQL superuser password. Default is `postgres`.
  - `POSTGRES_DB`: The name of the database to create on initialization. Default is `postgres`.
  - `PGDATA`: The storage path for PostgreSQL database data.
- **Volume**:
  - `postgres-data`: Used to persist PostgreSQL data.
- **Port Mapping**: `5432:5432` (Maps port 5432 on the host to port 5432 in the container).

### pgAdmin

- **Image**: `dpage/pgadmin4`
- **Environment Variables**:
  - `PGADMIN_DEFAULT_EMAIL`: The default email for logging into pgAdmin. Default is `admin@admin.com`.
  - `PGADMIN_DEFAULT_PASSWORD`: The default password for logging into pgAdmin. Default is `admin`.
- **Port Mapping**: `5431:80` (Maps port 5431 on the host to port 80 in the container).
- **Depends On**: Relies on the `postgres` service.

## Usage Instructions

1. Start the Services
   Run the following command in the directory containing the docker-compose.yml file to start PostgreSQL and pgAdmin services:

```bash
docker-compose up -d
```

2. Access pgAdmin:
   Open your browser and go to http://localhost:5431. Log in with admin@admin.com and admin. 4. Connect to PostgreSQL:
   In pgAdmin, you can add a new server connection with the following details:
   - Host Name/Address: postgres
   - Port: 5432
   - Maintenance Database: postgres
   - Username: postgres
   - Password: postgres
3. Stop the Services:
   If you need to stop the services, you can run:
   ```bash
   docker-compose down
   ```

## Notes

- Persistent Storage: PostgreSQL data is stored in the postgres-data volume, so data will persist even if the container is removed.
- Updates: You can update the PostgreSQL and pgAdmin image versions in the docker-compose.yml file as needed.
