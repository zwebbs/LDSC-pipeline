

## Build and Initialize Docker for LDSC

To build a docker container that can execute ldsc in its appropriate python 2.7 environment. We run the following code in ther terminal. This requires docker to be previously installed and running on the system with an available internet connection for downloading the base image.

```{bash}
cd docker
docker build -t ldsc:latest .
docker run -itd --name ldsc-docker ldsc:latest
```

To run any of the scripts in the ldsc suite, we can simply prepend the `docker exec` command to the script command. For example, to print the help message: 

```
# docker exec <container name> <command>
docker exec ldsc-docker python ldsc.py --help
```

