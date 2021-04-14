# Notifiarr Build Dependencies

This repo contains binaries and other obscure dependencies for Notifiarr.

## [notifiarr-docker-amd64.tgz](notifiarr-docker-amd64.tgz)

- This archive contains MegaCLI and smartctl for amd64.
- MegaCLI came from this [archive](https://srkdev.com/megacli/MegaCli-8.07.14-1.noarch.rpm).
- Smartctl came from [this archive](https://1276-105252244-gh.circle-artifacts.com/0/builds/smartmontools-linux-x86_64-static-7.3-r5214.tar.gz).
- Used by the [Dockerfile](https://github.com/Notifiarr/notifiarr/blob/main/init/docker/Dockerfile) for Notifiarr client.
