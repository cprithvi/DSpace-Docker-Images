{% include nav.html %}
## Windows 10 setup for Docker DSpace

### Install Docker Desktop

[https://docs.docker.com/docker-for-windows/install/](https://docs.docker.com/docker-for-windows/install/)

### Install Git Bash as a terminal for running Docker
_This shell most closely mirrors the user experience for MacOS and Linux users_

[https://git-scm.com/downloads](https://git-scm.com/downloads)

Run the following command to verify your install
```shell
  git version
```

### Note for Windows users running docker commands

- When running a DSpace command that requires terminal interaction, prefix your docker command with `winpty`
- When referencing a the root directory of a docker container, use `//` instead of `/`.  
  - Example use `//dspace/bin/dspace` for `/dspace/bin/dspace`

### Verify Running Docker from your Terminal

```shell
winpty docker run -it --rm ubuntu //bin/bash
```

Enter `echo hello` then enter `exit`

```
root@653eeaeb274b:/# echo hello
hello
root@653eeaeb274b:/# exit
exit
```

### Download DSpace Docker Compose Files

```shell
cd
git clone https://github.com/DSpace-Labs/DSpace-Docker-Images.git
cd DSpace-Docker-Images/docker-compose-files/dspace-compose
```

### Verify Docker Compose

```
docker-compose version
```

Check your download of DSpace Compose Files

```
docker-compose config | grep container_name
```

### Verify your memory allocation for Docker

_Note: DSpace Docker requires a minimum of 5-6G of RAM allocated to Docker in order to run._  

Run the following command to verify your memory allocation for Docker.

`docker info | grep Memory`

If less that 5G has been allocated to Docker, you can [configure memory for Docker](setup.Memory.md).

### Start using DSpace-Docker

- [Run DSpace 6](run.DSpace6.md)
- [Run DSpace 7](run.DSpace7.md)
- [Run DSpace 7 with Configurable Entities Data](run.DSpace7Entities.md)
