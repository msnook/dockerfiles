FROM ubuntu:bionic

ARG TERRAFORM_VERSION="1.0.7"
ARG ANSIBLE_VERSION="2.10"
ARG PACKER_VERSION="1.7.3"
ARG AWSCLI_VERSION="1.19.98"

# Install necessary utilities
RUN apt-get update && \
    apt-get install -y curl python3 python3-pip python3-boto unzip openssh-client

# Install aws cli
RUN pip3 install --upgrade awscli==${AWSCLI_VERSION}

# Install ansible
RUN apt-get install -y software-properties-common && \
    apt-add-repository -y --update ppa:ansible/ansible-${ANSIBLE_VERSION} && \
    apt-get update -y && \
    apt-get install -y ansible

# Install terraform
RUN curl -LO https://releases.hashicorp.com/terraform/${TERRAFORM_VERSION}/terraform_${TERRAFORM_VERSION}_linux_amd64.zip && \
    unzip -o *.zip -d /usr/local/bin && \
    rm *.zip

# Install packer
RUN curl -LO https://releases.hashicorp.com/packer/${PACKER_VERSION}/packer_${PACKER_VERSION}_linux_amd64.zip && \
    unzip -o *.zip -d /usr/local/bin && \
    rm *.zip

RUN apt-get clean && \
    rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/*

CMD    ["/bin/bash"]
