### `Docker: Do código ao Docker Compose`

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

