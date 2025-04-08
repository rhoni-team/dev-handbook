# Manage Postgres DB on Ubuntu Server

## Login to the postgres shell

```bash
psql -U <username>

```

## Inspect all the databases and its owners

```bash
\l
```

## Create a new database

```bash
CREATE DATABASE <database_name>;

# if necessary, add postgis extension
CREATE EXTENSION postgis;
```

## Inspect the database

```bash
\c <database_name>;
```

## Inspect the tables

```bash
\dt
```

## Delete a database

```bash
DROP DATABASE <database_name>;
```

## Create a new user

```bash
CREATE USER <username> WITH PASSWORD '<password>';
```

## Steps to recreate a database

```bash
# Login to the postgres shell
psql -U <username>

# Drop the database
DROP DATABASE <database_name>;

# Create the database
CREATE DATABASE <database_name>;

# Enter to the database
\c <database_name>;

# Add the postgis extension if necessary
CREATE EXTENSION postgis;
```
