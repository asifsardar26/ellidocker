# ellidocker

Dockerfiles for creating docker images containing build environment for:

- [Ell-i Runtime][3]
- [Robot Framework][5]
- [RIOT OS][4]

In RIOT OS, we are interested only in:

- Native platform
- Cortex-M development platform

### Docker install

To install docker, refer to [Docker Installation][1].

### Non-root access

To give non-root acess to docker client, please follow [Non-root Access][2].

### Pulling images

To pull image from dockerhub registry, run docker as 'docker pull IMAGE-NAME:TAG' e.g.

```
docker pull asifsardar26/ellidocker:32-bit
```

### Building images

To build a docker image, run the docker as 'docker build -t IMAGE-NAME PATH-TO-DOCKERFILE' e.g.

```
docker build -t ellidocker /path-to-dockerfile/Dockerfile
```

To rebuild the docker image with up to date software run:

```
docker build -t ellidocker /path-to-dockerfile/Dockerfile --no-cache
```

### Running images

To start the image run 'docker run -i -t IMAGE-NAME:TAG' e.g.

```
docker run -i -t asifsardar26/ellidocker:32-bit
```

- **Mounting data to docker images**

    The local data can be mounted to the images in order to build, run and compile:

    - Ell-i Runtime and Robot Tests
    - RIOT OS

    The local data is mounted to the built image as 'docker run -i -t -u $UID -v /path/to/working/directory:/home      IMAGE-NAME:TAG' e.g.

    For Ell-i Runtime and Robot Tests:

    ```
    docker run -i -t -v ~/Runtime/:/home/Runtime/ asifsardar26/ellidocker:32-bit
    ```

    For RIOT:

    ```
    docker run -i -t -u $UID -v ~/RIOT/:/home/RIOT/ asifsardar26/ellidocker:32-bit
    ```



[1]: https://docs.docker.com/installation/ubuntulinux/
[2]: https://docs.docker.com/installation/ubuntulinux/#giving-non-root-access
[3]: https://github.com/Ell-i/Runtime.git
[4]: https://github.com/RIOT-OS/RIOT.git
[5]: http://robotframework.org/
