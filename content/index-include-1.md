+++
date = "2015-06-07T19:03:22-07:00"
title = "Index"
include = "index-1"
+++

**runc is a CLI tool for spawning and running containers according to the OCP specification. The code can be found at [https://github.com/opencontainers/runc](https://github.com/opencontainers/runc).**


### runC characteristics:

* **Embeddable**: Containers are started as a child process of runC and there is no daemon that needs managing.
* **Battle hardened**: runC is built on libcontainer, the same container technology powering millions of Docker Engine installations.
* **Compatible with Docker**: Docker images can be ran with runC.

### Getting started

You can run Docker images pulled with Docker: first you need to run a container for that image, then export it's file system. 

```
$ docker export myapp > myapp.tar
$ tar xvf myapp.tar -C /tmp/myappfs
$ cd /tmp/myappfs
```

Or you can start with just a directory with a filesystem in it:

```
$ ls myapp
bin      etc      lib      linuxrc  mnt      proc     run      sys      usr
dev      home     lib64    media    opt      root     sbin     tmp      var
```

In that directory, create a manifest file for runC to run it, or let runC generate one for you.

```
$ runc spec > container.json
```

Edit container.json to specify the command you want to run inyour container, and any other options. 

Run the container!

```
$ runc
```

### Embedding

runc can be embedded into various other systems without having to run a Docker daemon.

### Systemd integration

runc does not create a dameon, so it integrates well with systemd.

```
[Unit]
Description=Minecraft Build Server
Documentation=http://minecraft.net
After=network.target

[Service]
CPUQuota=200%
MemoryLimit=1536M
ExecStart=/usr/local/bin/runc
Restart=on-failure
WorkingDirectory=/containers/minecraftbuild

[Install]
WantedBy=multi-user.target
```
