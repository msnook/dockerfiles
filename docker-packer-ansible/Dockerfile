FROM docker:20.10.6

ARG PACKER_VERSION="1.7.2"

# install packer
RUN wget https://releases.hashicorp.com/packer/${PACKER_VERSION}/packer_${PACKER_VERSION}_linux_amd64.zip && \
    unzip -o *.zip -d /usr/local/bin && \
    rm *.zip

# install ansible
RUN apk update && \
    apk upgrade && \
    apk add ansible
