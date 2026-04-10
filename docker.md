## General commands

`$ docker info` general info, image/container count, etc.

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

## Inside container commands

#### Networking

`$ hostname`

`$ hostname -I`

`$ cat /etc/hosts`

#### Other

`$ apt-get update; apt-get install vim` install package


## Inspecting containers

`$ docker top some_name` 

`$ docker exec some_name ps aux`

> Rule of thumb
docker top → quick inspection, debugging minimal containers
docker exec ps aux → detailed analysis when tools (ps) are available
