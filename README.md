# Tor hidden service on Docker

Create a tor hidden service with a link

```
# run a container with an network application
$ docker run -d --name hello_world tutum/hello_world

# and just link it to this container
$ docker run -ti --link hello_world fflo/tor-hidden-service
```

The .onion url is displayed to stdout at startup.

To keep onion keys, just mount volume `/var/lib/tor/hidden_service/`

```
$ docker run -ti --link something --volume /path/to/keys:/var/lib/tor/hidden_service/ fflo/tor-hidden-service
```

Look at the `docker-compose.yml` file to see own to use it.
