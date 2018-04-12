# About Docker

Docker provides a way to run applications securely isolated in a container,
packaged with all its dependencies and libraries. --
[docs.docker.com](https://docs.docker.com/)

A docker image with all software used during the following labs is prepared and
published on Dockerhub (kind of like a GitHub for Docker images). The images
have already been pulled to your lab computers.

Docker images can be loaded into _containers_, these are the actual virtual
machines. You will create a container and then use it in the remaining labs.

# Creating your own container

* Start Windows **WITH** Hypervisor.
* Start Docker (double click on the Docker icon on the Destop).

Docker takes a few minutes to start. You can check its status in the lower
right corner. It may fail to start if the host operating system cannot grant it
enough memory (its icon turns red in the status bar).

## Reducing its memory

Right click on the whale icon in the statusbar and open Settings. Under
Advanced, reduce the memory size to 1GB.

## Using Docker

Once Docker is running you can use it from PowerShell. Open Powershell and type
`docker info`. You should see a bunch of information about the host system and
Docker configuration.

`docker images` lists images available on the computer. You should see an image
called `juditacs/python-nlp`.

## Creating your container (Week 10)

**WARNING** This should only be run the first time you are creating a container
(Week 10's lab). See the next section on starting an existing container.

This command creates and starts a new container:

    docker run --name YOUR_NEPTUN_HERE -p 8088:8088 -it juditacs/python-nlp bash

Replace `YOUR_NEPTUN_HERE` with your own Neptun code. You will be able to use
this container in the remaining classes as well. The name is case sensitive.

`-p 8088:8088` forwards the container's 8088's port to the host machine's 8088
port. We will run Jupyter using this port.

You should see a Linux prompt similar to `root@78f84144684d:/nlp#`

`/nlp` is the directory we are going to work in. The repository is already
cloned but you should refresh it with:

    cd python_nlp_2018_spring; git pull

The container stops when all shells (you can use more than one) exit. You can
exit a Linux shell with Ctrl+D or by typing the command `exit`.

## Using your existing container (after Week 10)

Starting an existing container:

    docker start YOUR_NEPTUN_HERE

Starting a BASH shell in the container:

    docker exec -it YOUR_NEPTUN_HERE bash

## Running  Jupyter

Starting Jupyter on port 8088:

    jupyter notebook --port=8088 --no-browser --ip=0.0.0.0 --allow-root

Jupyter prints a long url that looks similar to this:

    http://0.0.0.0:8088/?token=67645360b5cfe5e940e0806bf7030a0a65af58173a80d0c7

Copy this URL into your favorite browser and **replace** 0.0.0.0 with
localhost.

## Using your own notebook

If you want to use your own notebook, you can

1. Install docker and launch a container on it,
2. Install packages required for the labs. Instructions for Ubuntu LTS are
   available in the Dockerfile (the `RUN` commands are normal shell commands).
   MacOS should be fairly similar. Both HFST and Foma have prebuilt Windows
   binaries.
