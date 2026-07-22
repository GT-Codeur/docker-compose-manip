# docker_compose_manip

A small Docker Compose project that launches a MySQL database and phpMyAdmin, and initializes a sample `users` table with test data.

## Contents

- `docker-compose.yml` - defines the MySQL and phpMyAdmin services.
- `init.sql` - database schema and seed data loaded automatically by MySQL on first startup.

## Prerequisites

- Docker
- Docker Compose

## Services

- `mysql` - MySQL server using `mysql:latest`
- `phpmyadmin` - phpMyAdmin UI for database management

## Database Configuration

- Database: `db_users`
- Root password: `mypassword`
- User: `myuser`
- Password: `pwd123456789`

## Getting Started

From the project root, run:

```bash
docker compose up -d
```

This will start both services in detached mode.

## Access phpMyAdmin

Open your browser at:

```text
http://localhost:8080
```

Login with:

- Server: `mysql`
- Username: `myuser`
- Password: `pwd123456789`

## Initialized Data

The database is seeded with a `users` table and three example rows:

- `John Doe` / `john@example.com`
- `Jane Smith` / `jane@example.com`
- `Thomas Johnson` / `thomass@example.com`

## Useful Commands

Start services:

```bash
docker compose up -d
```

Stop services:

```bash
docker compose down
```

View running containers:

```bash
docker compose ps
```

View MySQL logs:

```bash
docker compose logs mysql
```

## Notes

- The SQL file is mounted to `/docker-entrypoint-initdb.d/init.sql`, so it is executed only when MySQL initializes a new data directory.
- If you want to reset the database, remove the MySQL volume or container data and restart the stack.
