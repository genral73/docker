# Install Docker Engine on Ubuntu or Debian
- The contents of /var/lib/docker/, including images, containers, volumes, and networks, are preserved.

#### Uninstall old versions
1. Older versions of Docker were called docker, docker.io, or docker-engine. If these are installed, uninstall them:
```bash
sudo apt-get remove docker docker-engine docker.io containerd runc
```
#### SET UP THE REPOSITORY
1. Update the apt package index and install packages to allow apt to use a repository over HTTPS:
```bash
sudo apt-get update
sudo apt-get install apt-transport-https ca-certificates curl gnupg-agent software-properties-common
```

2. Add Docker’s official GPG key:
```bash
sudo curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -
```

3. Use the following command to set up the stable repository.
```bash
sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable"
```

#### INSTALL DOCKER ENGINE
1. Update the apt package index, and install the latest version of Docker Engine and containerd.
```bash
sudo apt-get update
sudo apt-get install docker-ce docker-ce-cli containerd.io
```

2. Verify that Docker Engine is installed correctly by running the hello-world image,this command downloads a test image and runs it in a container. When the container runs, it prints an informational message and exits.
```
sudo docker run hello-world
```
3. If you would like to use Docker as a non-root user, create the docker group.
```bash
sudo groupadd docker
```
4. Add your user to the docker group.
 ```bash
sudo usermod -aG docker $USER
```
5. Logout and login so that your group membership is re-evaluated, you can also run the following command to activate the changes to groups:
```bash
newgrp docker
```
6. Verify that you can run docker commands without `sudo`.
```bash
docker run hello-world
```
  Output should be:
>  Hello from Docker!
>  This message shows that your installation appears to be working correctly.
> 
>   To generate this message, Docker took the following steps:
>    1. The Docker client contacted the Docker daemon.
>    2. The Docker daemon pulled the "hello-world" image from the Docker Hub.
>       (amd64)
>    3. The Docker daemon created a new container from that image which runs the
>       executable that produces the output you are currently reading.
>    4. The Docker daemon streamed that output to the Docker client, which sent it
>       to your terminal.
> 
>   To try something more ambitious, you can run an Ubuntu container with:
>   $ docker run -it ubuntu bash
> 
>   Share images, automate workflows, and more with a free Docker ID:
>     https://hub.docker.com/
> 
>   For more examples and ideas, visit:
>     https://docs.docker.com/get-started/

## Where to go next
### [Install Docker Compose](https://github.com/genral73/docker-compose#install-compose-on-linux-systems)
