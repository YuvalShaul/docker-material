# Docker Basics

## Docker Versions
- [Docker desktop](https://docs.docker.com/desktop/)
  - This is a commercial tools for Mac/Linux/Windows.
  - Needs a subscription for organizations with more than 250 employees.
  - It installs many tools, including graphical tools.
- [Docker engine](https://docs.docker.com/engine/)  
  - Open source
  - Includes Docker daemon and cli

## Installing Docker Engine
- In most of my courses I install the docker-engine on Ubuntu.
- This is the [link to the installaion](https://docs.docker.com/engine/install/ubuntu/).


## Experiment with docker

- Run a container:  
**docker run -it busybox**
  - the [docker run](https://docs.docker.com/engine/reference/commandline/run/) command
  - the -it parameters:
    - --interactive , -i 		Keep STDIN open even if not attached
    - --tty , -t 		Allocate a pseudo-TTY
  - Use Linux command to the the details of your running container (files/directories networking)
  - exit (user the Linux **exit** command, or ctrl-d)
  - use **docker ps** to see running containers  
  (so your container is not there)
  - use **docker ps -a** to see all containers  
  (yes, it has already exited)


