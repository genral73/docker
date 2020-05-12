# Install Docker Engine on Ubuntu
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
3. If you would like to use Docker as a non-root user, you should now consider adding your user to the “docker” group with something like, remember to log out and back in for this to take effect!:

```bash
sudo usermod -aG docker $USER
```

- The contents of /var/lib/docker/, including images, containers, volumes, and networks, are preserved.

