ARG ARCH
FROM multiarch/debian-debootstrap:${ARCH}-bullseye
LABEL version="4"

RUN dpkg --add-architecture arm64 && \
    apt-get update -qq && \
    apt-get upgrade -y && \
    apt-get dist-upgrade -y && \
    apt-get install -y gcc \
       cmake ninja-build \
       autoconf automake git libssl-dev libtool make unzip wget zlib1g-dev \
       doxygen  \
       python3 python3-nose python3-rednose python3-pytest python3-pytest-xdist docker.io \
       python3-psutil \
       maven openjdk-11-jdk \
       gcc-arm-linux-gnueabi gcc-arm-linux-gnueabihf gcc-aarch64-linux-gnu qemu-user-static \
       libssl-dev:arm64

ENV JAVA_HOME=/usr/lib/jvm/java-1.11.0-openjdk-amd64

# de-comment to add go for BoringSSL testing: 
#    && \
#    wget https://dl.google.com/go/go1.14.3.linux-amd64.tar.gz && \
#    tar -C /usr/local -xzf go1.14.3.linux-amd64.tar.gz && \
#    cp /usr/local/go/bin/* /usr/bin 

