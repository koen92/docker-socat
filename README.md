# docker-socat

Tiny container with socat binary. Useful for running as sidecar


Example for routing arbritrary TCP traffic trough a corporate proxy:

```
# docker run -p 8080:8080 --entrypoint=/bin/socat koen92/docker-socat TCP-listen:8080,reuseaddr,forever,fork PROXY:INSERT_PROXY_HOST:DESTINATION_HOST:DESTINATION_PORT,proxyport=INSERT_PROXY_PORT,forever
```

For quick debugging, busybox is included. You can start this container with a debug shell with this command:

```
# docker run -ti --entrypoint=/bin/busybox koen92/docker-socat
```
