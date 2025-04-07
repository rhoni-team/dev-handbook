# Update site on Ubuntu server

Start by updating the github repository and pulling the changes.

## 1) Inspect docker volumes

List all the docker volumes to find the name of the volume for the site.

```bash
docker volume ls
```

## 2) Stop the site container and the nginx container.

Both containers must be stopped to allow the volume to be updated.

```bash
# step on NGINX folder

docker compose down

# step on the SITE folder

docker compose down
```

## 3) Remove the volume

```bash
docker volume rm <volume_name>
```

## 4) Rebuild the container without cache

```bash
docker compose build --no-cache
```

## 5) Build the static files

If it is a django vue site, first build the static files from the vue app:

```bash
# step on the site folder
cd frontend
npm run build
```

Then build the django app:

```bash
# step on the site folder
cd backend
python manage.py collectstatic --noinput
```

## 6) Restart the site container

```bash
docker compose up -d
```

## 7) Inspect the container to see if the new files were copied

```bash
# Enter the container to see the files
docker exec -it <container_name> bash
# Run a busybox container to inspect the files
docker run --rm -it -v <volume_name>:/mnt busybox sh
# Enter the volume
cd /mnt
# List the files
ls
# Exit the busybox container
exit
# Exit the container
exit
```

## 8) Restart the nginx container

```bash
# step on nginx folder
docker compose up -d
```
