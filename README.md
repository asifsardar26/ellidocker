# ellidocker

Dockerfiles for creating docker images containing build environment for:

- Ell-i Runtime
- Robot Framework
- RIOT OS

In RIOT OS, we are interested only in:

- Native platform
- Cortex-M development platform

### Docker install

To install docker, refer to [Docker Installation][1].

### Non-root access

To give non-root acess to docker client, please follow [Non-root Access][2].

### Pulling images

To pull image from dockerhub registry, run docker as **docker pull IMAGE-NAME:TAG** e.g.

...
docker pull asifsardar26/ellidocker:32-bit
...

### Building images

To build a docker image, run the docker as **docker build -t IMAGE-NAME PATH-TO-DOCKERFILE** e.g.

...
docker build -t ellidocker /path-to-dockerfile/Dockerfile
...

To rebuild the docker image with up to date software run:

...
docker build -t ellidocker /path-to-dockerfile/Dockerfile --no-cache
...

### Running images

- **Mounting data to docker images**

---> Work in progress



[1]: https://docs.docker.com/installation/ubuntulinux/
[2]: https://docs.docker.com/installation/ubuntulinux/#giving-non-root-access
