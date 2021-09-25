# Deploying-registry-Docker

A Docker registry is a system for versioning, storing and distributing Docker images

Steps to create a registry and place an image in it-

```

1. Run the following command to start the registry container:
$ sudo docker run -d -p 5000:5000 --restart=always --name registry registry:2

2. List the running containers to check the newly created container-
$ sudo docker ps

3. Copy an image from Docker Hub to your registry
$ sudo docker pull ubuntu:16.04
$ sudo docker tag ubuntu:16.04 localhost:5000/my-ubuntu
$ sudo docker images  

4. Push the image to the local registry using the command:
$ sudo docker push localhost:5000/my-ubuntu

5. Remove the locally cached images using the command:
$ sudo docker image remove ubuntu:16.04
$ sudo docker image remove localhost:5000/my-ubuntu

6. Pull the localhost:5000/my-ubuntu image from the local registry
$ sudo docker pull localhost:5000/my-ubuntu

7. Stop the running registry
$ sudo docker container stop registry

```
