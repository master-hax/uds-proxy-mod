# uds-proxy-mod

a [Docker Mod](https://github.com/linuxserver/docker-mods) for [linuxserver.io](https://www.linuxserver.io/) containers that installs nginx & sets it up to proxy HTTP services to [Unix domain sockets](https://en.wikipedia.org/wiki/Unix_domain_socket), allowing for direct container to container communication through volumes.

## setup

First, add the variable `DOCKER_MODS=ghcr.io/master-hax/uds-proxy-mod:latest` in the linuxserver container. Then use the following variables to customize the configuration.

| Env Name | Env Value | Function |
| :----: | :---: | --- |
| `UDS_PROXY_HOST_<host_name/socket_name>` | <proxy_target> | (required) the name of the socket file to be created & the proxy target e.g. UDS_PROXY_HOST_deluge=localhost:8112 or UDS_PROXY_HOST_prowlarr=localhost:6969 |
| `UDS_PROXY_SOCK_LOCATION` | <socket_directory> | (optional) the directory in which to create the unix domain socket. defaults to "/comm"
| `UDS_PROXY_CONF_LOCATION` | <nginx_conf_directory> | (optional) the directory in which to create the nginx.conf file. defaults to "/etc/nginx" |
