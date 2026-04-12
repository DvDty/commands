## General commands

`$ docker info` general info, image/container count, etc.

`$ docker ps` containers
- `-a` all
- `-q` just ids 

`$ docker images`

`$ docker pull ubuntu:18.04` download image

`$ docker run -it ubuntu /bin/bash` run container

`$ docker run -it --name some_name ubuntu /bin/bash` with name

`$ docker ps -a` all containers

`$ docker start aa3f365f0f4e` start container

`$ docker -d ubuntu /bin/sh -c "while true; do echo hello world; sleep 1; done"` long running container

`$ docker logs some_name` logs
- `-f` follow
- `--tail` last x lines
- `-t` with timestamps

`$ docker logs -ft some_name` new logs

`$ docker rm 80430f8d0921` delete container


## Inspecting containers

`$ docker top some_name` 

`$ docker exec some_name ps aux`

> Rule of thumb <br>
docker top → quick inspection, debugging minimal containers <br>
docker exec ps aux → detailed analysis when tools (ps) are available

`$ docker stats some_name` CPU, memory, network, storage I/O performance, metrics

`$ docker inspect some_name` configuration information, including names, commands, networking configuration

`$ docker history some_name` check layer commands

`$ docker port some_name 80` check port info

`$ hostname`

`$ hostname -I`

`$ cat /etc/hosts`


## Dockerfile

`RUN ` build time commands

`CMD ` runtime command, only 1 per Dockerfile

`ENTRYPOINT ` bin to execute, CMD commands are passed as arguments to ENTRYPOINT

> `$ docker run -it some/image:latest -g "param;"` <br>
`CMD` is the default param, could be overriten by `-g` when starting the container
