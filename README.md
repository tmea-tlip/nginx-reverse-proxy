# nginx-reverse-proxy

Instructions on how to set up a reverse proxy for one-click-tangle

### Prerequisites

Ensure you have Docker and Docker Compose. Docker Compose is a tool for defining and running multi-container Docker applications. A series YAML files are used to configure the required services. This means all container services can be brought up in a single command. Docker Compose is installed by default as part of Docker for Windows and Docker for Mac, however Linux users will need to follow separate instructions.

You can check your current Docker and Docker Compose versions using the following commands:

```
docker-compose -v
docker version
```

Please ensure that you are using Docker version 18.03 or higher and Docker Compose 1.21 or higher and upgrade if necessary.

You should also have the **origin-server.crt** which is an origin server certificate file and **origin-server.key** which is an origin server certificate private key. Services that provide this for a given domain are [let's encrypt](https://letsencrypt.org/) and [cloudfare](https://www.cloudflare.com/). the files should be stored in the `/nginx-reverse-proxy-ssl/nginx-conf/` directory.

### Running

After cloning the repository, go to the `nginx-reverse-proxy-ssl` directory

```
cd nginx-reverse-proxy-ssl
```

Then run the docker container containing nginx by running

```
docker-compose --log-level ERROR up -d
```

### Operations

To run the nginx-reverse-proxy docker container, run

```
docker-compose --log-level ERROR up -d
```

To stop the nginx-reverse-proxy docker container, run

```
docker-compose stop nginx-rproxy-ssl
```

To check the logs for the docker container, run

```
docker ps
```

Once you have identified the container id of the running nginx node you can then run

```
docker logs -f container-id
```

Replacing **container-id** with the id of the running **nginx-rproxy-ssl** container

## License

This project is licensed under the MIT License - see the [LICENSE.md](LICENSE) file for details
