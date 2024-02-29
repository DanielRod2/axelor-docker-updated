# Axelor Dockerfiles

This repository provides [Dockerfiles](https://docs.docker.com/engine/reference/builder/) and samples to build [Docker](https://www.docker.com/what-docker) images for [Axelor](https://axelor.com) apps.

## Build Images

It assumes you have Docker installed on your system.

### Build base image

```sh
$ cd aio-base
$ docker build -t axelor/aio-base .

```

## Run app container

Once app image is built, get the image and can run it like this:

```sh
$ curl -OL https://github.com/axelor/open-suite-webapp/releases/download/v8.0.1/axelor-erp-v8.0.1.war
$ docker run -p 8080:80  -d -v ./axelor-erp-v8.0.1.war:/var/lib/tomcat/webapps/ROOT.war axelor/aio-base
```

Once app completes database initialization, it can be access at: http://localhost:8080

