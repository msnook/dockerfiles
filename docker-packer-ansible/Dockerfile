FROM docker:20.10.6

ARG PACKER_VERSION="1.7.2"
ARG ANSIBLE_VERSION="2.9.21"

# install necessary utilities
RUN apk update && \
    apk upgrade && \
    apk add --update python3 py3-pip openssl ca-certificates && \
    apk --update add --virtual build-dependencies python3-dev libffi-dev openssl-dev build-base && \
    pip3 install --upgrade pip

# install packer
RUN wget https://releases.hashicorp.com/packer/${PACKER_VERSION}/packer_${PACKER_VERSION}_linux_amd64.zip && \
    unzip -o *.zip -d /usr/local/bin && \
    rm *.zip

# install ansible
RUN CRYPTOGRAPHY_DONT_BUILD_RUST=1 pip3 install ansible==${ANSIBLE_VERSION}

# clean up
RUN apk del build-dependencies && \
    rm -rf /var/cache/apk/* \
