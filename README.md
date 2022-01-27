## `Docker: Do código ao Docker Compose`

### `Installing Docker`

1. Before you get started, please make sure you have Docker installed on your machine:

```
curl -fsSl https://get.docker.com
```

1.1. Make sure Docker service is running state:

```
docker-tutorialz]#  systemctl status docker
● docker.service - Docker Application Container Engine
   Loaded: loaded (/usr/lib/systemd/system/docker.service; enabled; vendor preset: disabled)
   Active: active (running) since Qua 2022-01-26 22:49:42 -03; 7min ago
     Docs: https://docs.docker.com
 Main PID: 4627 (dockerd)
   CGroup: /system.slice/docker.service
           └─4627 /usr/bin/dockerd -H fd:// --containerd=/run/containerd/containerd.sock

Jan 26 22:49:41 elliot01 dockerd[4627]: time="2022-01-26T22:49:41.146036873-03:00" level=info msg="Firewalld: interface docker_gwbridge already part of docke...returning"
Jan 26 22:49:41 elliot01 dockerd[4627]: time="2022-01-26T22:49:41.599628089-03:00" level=info msg="Default bridge (docker0) is assigned with an IP address 17...P address"
Jan 26 22:49:41 elliot01 dockerd[4627]: time="2022-01-26T22:49:41.792362351-03:00" level=info msg="Firewalld: interface docker0 already part of docker zone, returning"
Jan 26 22:49:42 elliot01 dockerd[4627]: time="2022-01-26T22:49:42.097403857-03:00" level=info msg="Loading containers: done."
Jan 26 22:49:42 elliot01 dockerd[4627]: time="2022-01-26T22:49:42.150425305-03:00" level=info msg="Docker daemon" commit=459d0df graphdriver(s)=devicemapper ...n=20.10.12
Jan 26 22:49:42 elliot01 dockerd[4627]: time="2022-01-26T22:49:42.168178372-03:00" level=error msg="cluster exited with error: error while loading TLS certificate in /...
Jan 26 22:49:42 elliot01 dockerd[4627]: time="2022-01-26T22:49:42.168284653-03:00" level=error msg="swarm component could not be started" error="error while loading TL...
Jan 26 22:49:42 elliot01 dockerd[4627]: time="2022-01-26T22:49:42.168340202-03:00" level=info msg="Daemon has completed initialization"
Jan 26 22:49:42 elliot01 systemd[1]: Started Docker Application Container Engine.
Jan 26 22:49:42 elliot01 dockerd[4627]: time="2022-01-26T22:49:42.231763910-03:00" level=info msg="API listen on /var/run/docker.sock"
Hint: Some lines were ellipsized, use -l to show in full.
```

### `Docker: Basic commands`

1. Before we need test a container image to demonstrate a `docker container run` command:

```
docker-tutorialz]# docker container run hello-world
Unable to find image 'hello-world:latest' locally
latest: Pulling from library/hello-world
2db29710123e: Pull complete
Digest: sha256:507ecde44b8eb741278274653120c2bf793b174c06ff4eaa672b713b3263477b
Status: Downloaded newer image for hello-world:latest

Hello from Docker!
This message shows that your installation appears to be working correctly.

To generate this message, Docker took the following steps:
 1. The Docker client contacted the Docker daemon.
 2. The Docker daemon pulled the "hello-world" image from the Docker Hub.
    (amd64)
 3. The Docker daemon created a new container from that image which runs the
    executable that produces the output you are currently reading.
 4. The Docker daemon streamed that output to the Docker client, which sent it
    to your terminal.

To try something more ambitious, you can run an Ubuntu container with:
 $ docker run -it ubuntu bash

Share images, automate workflows, and more with a free Docker ID:
 https://hub.docker.com/

For more examples and ideas, visit:
 https://docs.docker.com/get-started/
```

1.1. List all Docker containers:

```
docker-tutorialz]# docker container ls
CONTAINER ID   IMAGE     COMMAND   CREATED   STATUS    PORTS     NAMES
[root@elliot01 docker-tutorialz]# docker container ls -a
CONTAINER ID   IMAGE           COMMAND                  CREATED         STATUS                     PORTS     NAMES
ea850619834e   hello-world     "/hello"                 2 minutes ago   Exited (0) 2 minutes ago             objective_haslett
ea3d6cba32ce   nginx:latest    "/docker-entrypoint.…"   2 months ago    Exited (255) 6 weeks ago   80/tcp    amaury.2.no71j9ujjjoj14u8bi62vqx5y
79151c794c62   nginx:latest    "/docker-entrypoint.…"   2 months ago    Exited (255) 6 weeks ago   80/tcp    amaury.3.bkbp2ugc5xoh1fagt02ha6nso
73a12ad1f474   nginx:latest    "/docker-entrypoint.…"   2 months ago    Exited (255) 6 weeks ago   80/tcp    amaury.1.tsmucyxcwftavjvy3vnzrcx40
2aaf276affba   alpine:latest   "ping 8.8.8.8"           2 months ago    Dead                                 eager_gates.2.pslfwckn3sc0gfl6mq5wrvy36
c00037dfdb53   nginx:latest    "/docker-entrypoint.…"   2 months ago    Exited (0) 2 months ago              amaury.1.vqdl6rxuu0x30o6jchlh66iqt
```

1.2. Set a name for my Docker container:

```
 docker-tutorialz]# docker container run --name amaury hello-world
```

1.3. List the containers:

```
docker-tutorialz]# docker container ls -a
CONTAINER ID   IMAGE           COMMAND                  CREATED         STATUS                     PORTS     NAMES
cead5b46cf1e   hello-world     "/hello"                 5 seconds ago   Exited (0) 3 seconds ago             amaury
```

1.4. Other way to create a new container using `-ti` option to interatic with container:

```
docker-tutorialz]# docker container run -ti ubuntu bash
Unable to find image 'ubuntu:latest' locally
latest: Pulling from library/ubuntu
ea362f368469: Pull complete
Digest: sha256:b5a61709a9a44284d88fb12e5c48db0409cfad5b69d4ff8224077c57302df9cf
Status: Downloaded newer image for ubuntu:latest
root@804841b67ea6:/#
```

1.5. Creating a MongoDB on Docker container:
- before we need check the Dockerhub about [MongoDB](https://hub.docker.com/_/mongo)

```
elliot01 ~]# docker container run -d -e MONGO_INITDB_ROOT_USERNAME=mongouser -e MONGO_INITDB_ROOT_PASSWORD=mongopwd mongo
2833a64a61b6637c77e4df70cdf2442ccd56b19dc1d63037307cb69497b2178a
```


