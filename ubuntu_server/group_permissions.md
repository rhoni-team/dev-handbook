# Group permissions on Ubuntu Server


# Create a new group

## Create a new group

```bash
sudo addgroup <group_name>
```

## Add a user to a group

```bash
sudo usermod -a -G <group_name> <user_name>
```

## Inspect the groups of a user

```bash
groups <user_name>
```

## Inspect the users of a group

```bash
getent group <group_name>
```


# Inspect permissions

## Inspect the permissions of a file

```bash
ls -l <file_name>
```

## Inspect the permissions of a directory

```bash
ls -la <directory_name>
```

# Change permissions

## Change group owner of a directory

```bash
sudo chgrp -R <group_name> <path>
```

## Give write permissions to a group

```bash
sudo chmod -R g+w <path>
```

## Give write permissions to a group for new files

```bash
chmod g+s <path>

# this gives the permissions:
# -rw-rw-r--
# owner can read, write
# group can read, write
# others can read
```
