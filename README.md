# MATSim Docker image

[![Docker Publish](https://github.com/maptic/matsim-docker/actions/workflows/docker-publish.yml/badge.svg)](https://github.com/maptic/matsim-docker/actions/workflows/docker-publish.yml)
[![Java CI with Maven](https://github.com/maptic/matsim-docker/actions/workflows/maven-ci.yml/badge.svg)](https://github.com/maptic/matsim-docker/actions/workflows/maven-ci.yml)

A docker image of the MATSim open-source framework:

* Container calls the main method of the `DockerEntrypoint` class when started.
* Provide input files with `config.xml` and save output files from the container using volumes.
* Make sure the `config.xml` is configured to output the information to  `/opt/matsim/data/output/`

```<param name="outputDirectory" value="/opt/matsim/data/output/" />```
  
* Pass additional arguments to MATSim using commands that are following the run statement.

## Getting started

Run MATSim inside a container:

```sh
docker run \
    -v <host/path/to/input>:/opt/matsim/data/input:ro \
    -v <host/path/to/output>:/opt/matsim/data/output \
    maptic/matsim:latest <optional MATSIM-ARGS>
```

To pull the recent version of the image, refer to the `latest` tag.

Make sure 
## Local build and development

Set the input and output path in the `docker-compose.yml` file, then run:

```sh
docker-compose build
docker-compose up
```

## References

* [DockerHub maptic/matsim](https://hub.docker.com/r/maptic/matsim)
* [MATSim Libs](https://github.com/matsim-org/matsim-libs)
* [MATSim Example](https://github.com/matsim-org/matsim-example-project)
