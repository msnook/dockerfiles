# ansible-packer-terraform

This Dockerfile, based on Ubuntu, contains the following:
  
  * terraform  - v0.12.23
  * ansible    - v2.9
  * packer     - v1.7.2
  * aws cli    - v1.19.0

## Use Case

This Dockerfile is ideal for use as a one-stop-shop for primary tools needed in a simple CI/CD pipeline.

## Building and Pushing to Dockerhub

To build:

```
docker build . -t msnook/ansible-packer-terraform
```

To push:

```
docker login
docker push msnook/ansible-packer-terraform
```
