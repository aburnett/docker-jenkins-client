Jenkins image with the docker client installed for cases were you want to run docker commands from Jenkins but connect to a daemon running elsewhere. The docker daemon is *not* running inside of the container.

# Usage
## Using the same docker host as the container

    docker run -v /var/run/docker.sock:/var/run/docker.sock docker-jenkins-client

## Using a remote docker host

    docker run -e DOCKER_HOST="tcp://10.10.10.10:2760" docker-jenkins-client

## Environment Variables

`DOCKER_OPTS` - additional `docker` command line arguments. e.g.

    docker run -e DOCKER_OPTS="-l debug" -v /var/run/docker.sock:/var/run/docker.sock docker-jenkins-client
