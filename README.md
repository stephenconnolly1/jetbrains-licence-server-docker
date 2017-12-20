# jetbrains-licence-server-docker

Docker image for the Java-based JetBrains License Server
https://www.jetbrains.com/help/license_server/getting_started.html

The default hostname and port are hardcoded into the container as they are configured at build time
If you need to re-configure these at runtime, you will need to override the ENTRYPOINT on
the command line.
Similarly if you need to configure the server to negotiate a proxy, you will need to includes
the configuration commands into the ENTRYPOINT

There is an automated build for this repository in [DockerHub](https://cloud.docker.com/app/stephenconnolly/repository/docker/stephenconnolly/jetbrains-licence-server-docker)

## Build

```
$ docker build -t jetbrains-licence-server .
```

## Run

```
docker run --rm -it -p 1017:1017 jetbrains-license-server
```

## Usage

Once the container is running, it will be listening on: http://localhost:1017/
To test the phone-home capability (i.e. proxy configuration) http://localhost:1017/check-connection
