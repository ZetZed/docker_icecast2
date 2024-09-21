## docker_icecast2

[![License](https://img.shields.io/github/license/ZetZed/docker_icecast2)](https://github.com/ZetZed/docker_icecast2/blob/master/LICENSE)

Simple Dockerfile for running [icecast2](https://icecast.org/) in a container. \
Just mount your icecast.xml file and you are good to go!

Works well with containerized [Liquidsoap](https://www.liquidsoap.info/): [ZetZed/docker_liquidsoap](https://github.com/ZetZed/docker_liquidsoap)

### Installation
- Build the image yourself
  - `docker build -t ZetZed/icecast2 github.com/ZetZed/docker_icecast2`

### Configuration
- Mount your icecast.xml to `/etc/icecast2/icecast.xml`
- Publish necessary ports

#### docker run
```
docker run --name icecast2 -d --restart=always \
--publish 8000:8000 \
--volume /path/to/your/icecast.xml:/etc/icecast2/icecast.xml \
ZetZed/icecast2
```
#### docker-compose.yml
```
icecast2:
  image: ZetZed/icecast2
  container_name: icecast2
  restart: always
  ports:
    - 8000:8000
  volumes:
    - /path/to/your/icecast.xml:/etc/icecast2/icecast.xml
```
