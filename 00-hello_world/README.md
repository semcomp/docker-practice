# 00 - Hello World

### Level 1
Just create a container that prints "Hello World" then stops.

```shell
# COMMAND
echo "Hello World"
```

### Level 2
Create a container that prints "Hello World" each 2 seconds.

```shell
# COMMAND
while true; do echo "Hello World"; sleep 2; done;
```

### Level 3
Create a container that run the script `lvl3.sh` in this folder.

### Level 4
Read the script `lvl4.sh` and create a container that run this script and prints the correct phrase using environment variables.
