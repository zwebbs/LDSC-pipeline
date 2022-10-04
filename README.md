

## Build and Initialize Docker for LDSC

To build a docker container that can execute ldsc in its appropriate python 2.7 environment, we run the following code in ther terminal. This requires docker to be previously installed and running on the system with an available internet connection for downloading the base image. One or more docker commands may require super user privelleges depending on your system administration.

```{bash}
docker build -t ldsc:latest docker/
docker run -itd \
    --name ldsc-docker \
    -v `pwd`/data/:/usr/src/app/ldsc/data/ \
    ldsc:latest
```

To execute any of the scripts in the ldsc suite, we can simply prepend the `docker exec <container name>` command to the script command. For example, to print the help message: 

```{bash}
docker exec ldsc-docker python ldsc.py --help
```

