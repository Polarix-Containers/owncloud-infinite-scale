# ownCloud Infinite Scale

![Build latest, scan & push](https://github.com/Polarix-Containers/owncloud-infinite-scale/actions/workflows/build-latest.yml/badge.svg)
![Build rolling, scan & push](https://github.com/Polarix-Containers/owncloud-infinite-scale/actions/workflows/build-rolling.yml/badge.svg)

### Features & usage
- Built on the [official image](https://github.com/owncloud/ocis) to be used as a drop-in replacement. Comes with regular rebuilds and hardened_malloc which are standard among Polarix containers.
- Unprivileged image: you should check your volumes' permissions (eg `/data`), default UID/GID is 200004. We changed from the default UID 1000 as it often belongs to a `wheel` user.

### Licensing
- The code in this repository is licensed under the Apache license. 😇
- The image is built on `docker.io/owncloud/ocis`, which is under the Apache license. Copyright to the base image belongs to ownCloud Inc.
- Any image built by Polarix Containers is provided under the combination of license terms resulting from the use of individual packages.
