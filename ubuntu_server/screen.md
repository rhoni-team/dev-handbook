# Using _screen_ to manage multiple terminals

## Open screen in the terminal

```bash
# Open screen in the terminal

screen

# then press enter
```


## Useful commands

**Create a new window**

```bash
Ctrl-a c
```

**Switch to the next window**

```bash
Ctrl-a n
```

**Switch to the previous window**

```bash
Ctrl-a p
```

# Session management

**List sessions**

```bash
screen -ls
```

**Attach to a session**

```bash
# the session name is the number that appears in the beginning of the line
# 1350821.pts-1.rhoni-server -> session name is 1350821
screen -r <session_name>
```
