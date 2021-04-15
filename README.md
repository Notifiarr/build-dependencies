# Notifiarr Build Dependencies

This repo contains binaries and other obscure dependencies for Notifiarr.

## [notifiarr-docker-amd64.tgz](notifiarr-docker-amd64.tgz)

- This archive contains `MegaCli64` and `smartctl` for amd64/x86_64.
- MegaCLI came from this [archive](https://srkdev.com/megacli/MegaCli-8.07.14-1.noarch.rpm).
- Smartctl was compiled from source on an Ubuntu Bionic VM.
- Used by the [Dockerfile](https://github.com/Notifiarr/notifiarr/blob/main/init/docker/Dockerfile) for Notifiarr client.

## [notifiarr-docker-i386.tgz](notifiarr-docker-i386.tgz)

- This archive contains `MegaCli32` and `smartctl` for i386/x86.
- MegaCLI came from this [archive](https://srkdev.com/megacli/MegaCli-8.07.14-1.noarch.rpm).
- Smartctl was compiled from source on an Ubuntu Bionic VM.
- Used by the [Dockerfile](https://github.com/Notifiarr/notifiarr/blob/main/init/docker/Dockerfile) for Notifiarr client.

Built using this `Dockerfile`:
```dockerfile
FROM i386/ubuntu as builder

RUN apt update && \
    apt install -y upx curl build-essential && \
    mkdir /build && \
    curl -sLS https://sourceforge.net/projects/smartmontools/files/smartmontools/7.2/smartmontools-7.2.tar.gz/download | \
    tar -zxC /build && \
    cd /build/smartmontools* && \
    ./configure LDFLAGS="-static" && \
    make && \
    upx -9 smartctl
```

## [notifiarr-docker-arm64.tgz](notifiarr-docker-arm64.tgz)

- This archive contains `smartctl` for arm64 (`aarch64`).
- MegaCLI is not available for ARM architecture.
- Contains dummy/empty files for megacli.
- Smartctl was compiled from source on an Ubuntu Bionic Rasperry Pi.

## [notifiarr-docker-armhf.tgz](notifiarr-docker-armhf.tgz)

- This archive contains `smartctl` for armhf (32 bit ARM).
- MegaCLI is not available for ARM architecture.
- Contains dummy/empty files for megacli.
- Smartctl was compiled from source on an Ubuntu Bionic Rasperry Pi.
