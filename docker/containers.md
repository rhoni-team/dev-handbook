# Docker containers

## List containers

**List running containers**
```bash
docker ps
```

**List all containers (running and stopped)**

```bash
docker ps -a
```

**List containers by name**

```bash
docker ps --filter "name=<container_name>"
```

## Build a container with docker compose

```bash
docker compose build
```

**Build a container without cache**

```bash
docker compose build --no-cache
```

## Managing containers

**Enter to the bash of a container**

```bash
docker exec -it <container_name> bash
```

**Inspect tables in a postgres container**

```bash
docker exec -it <container_name> bash
psql -U <username> -d <database_name>
\dt
```

