




## Setting up the analysis environment

The analysis pipeline is built almost entirely in python3, but because LDSC relies on python2, we require access to two incompatible python environments. To resolve this issue, we've chosen to implement a python3 virtual environment for the bulk of the work, and a docker container for specific calls to LDSC.    

### Build and Initialize Docker for LDSC

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

