# Base image
FROM ubuntu:24.04

RUN apt update && \
    apt install -y git wget sudo openssh-server zsh curl nano build-essential libssl-dev pkg-config protobuf-compiler libclang1 clang \
       cmake \
        libpq-dev \
        libdw-dev \
        binutils \
        lld \
        libudev-dev \
        iputils-ping \
        iproute2 && \
    rm -rf /var/lib/apt/lists/*

# Copy the install.sh script into the container
COPY install.sh /usr/local/bin/install.sh

# Make the script executable
RUN chmod +x /usr/local/bin/install.sh

# Run the script during the build process
RUN /usr/local/bin/install.sh
