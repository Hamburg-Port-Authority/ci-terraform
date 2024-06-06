FROM python:3.10-alpine

# Versions
ARG TERRAFORM_VERSION=1.6.6

# install python build dependencies
RUN apk --no-cache add \
    gcc \
    musl-dev \
    libffi-dev \
    make \
    bash \
    openssl \
    curl \
    pcre2-tools \
    grep \
    git \
    jq \
    nano \
    apache2-utils

# update pip
RUN pip3 install --upgrade pip

# install azure cli
RUN pip3 install azure-cli

# Installing Terraform
RUN curl -O https://releases.hashicorp.com/terraform/${TERRAFORM_VERSION}/terraform_${TERRAFORM_VERSION}_linux_amd64.zip \
    && unzip terraform_${TERRAFORM_VERSION}_linux_amd64.zip -d /usr/bin \
    && rm terraform_${TERRAFORM_VERSION}_linux_amd64.zip

# setup
ENTRYPOINT ["/bin/sh", "-c"]
CMD ["bash"]
