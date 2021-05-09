# docker-packer-ansible

This Dockerfile, based on Alpine Linux, contains the following:
  
  * docker  - v20.10.6
  * ansible - (latest from Alpine Linux)
  * packer  - v1.7.2

## Use Case

A potential use case for this Dockerfile might be leveraging Packer's [Docker builder](https://www.packer.io/docs/builders/docker) to build a Docker image using Ansible playbooks referenced from a Packer configuration.

## Building and Pushing to Dockerhub

To build:

```
docker build . -t msnook/docker-packer-ansible:latest
```

To tag using latest commit SHA:

```
tag=`git rev-parse --short HEAD`
docker tag msnook/docker-packer-ansible:latest msnook/docker-packer-ansible:$tag
```

To push:

```
docker login
docker push msnook/docker-packer-ansible:$tag
docker push msnook/docker-packer-ansible:latest (if desired)
```
