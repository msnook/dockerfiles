# ansible-packer-terraform

This Dockerfile, based on Ubuntu, contains the following:
  
  * terraform  - v1.0.5
  * ansible    - v2.10.x
  * packer     - v1.7.3
  * aws cli    - v1.19.98

## Use Case

This Dockerfile is ideal for use as a one-stop-shop for primary tools needed in a simple CI/CD pipeline.

## Building and Pushing to Dockerhub

To build:

```
docker build . -t msnook/ansible-packer-terraform:latest
```

To tag using latest commit SHA:

```
tag=`git rev-parse --short HEAD`
docker tag msnook/ansible-packer-terraform:latest msnook/ansible-packer-terraform:$tag
```

To push:

```
docker login
docker push msnook/ansible-packer-terraform:$tag
docker push msnook/ansible-packer-terraform:latest (if desired)
```
