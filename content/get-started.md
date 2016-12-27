+++
date = "2016-12-26T14:45:30+11:00"
title = "Get Started"
include = "get-started"
+++

## Getting started

runC only requires a root filesystem and a configuration in order to start containers.

Creation and extraction of root filesystems is beyond the scope of runC, however you could use Docker to generate a filesystem for a runC container.

```
$ mkdir /tmp/myapp/rootfs
$ docker export myapp | tar xvfC - /tmp/myapp/rootfs
```

The OCI also defines an [image specification][oci-image], and there are a variety of tools that are available that also allow you to create a root filesystem using OCI images.
Examples of such tools include [oci-image-tools][oci-image-tools], [skopeo][skopeo], and [umoci][umoci].

```
$ skopeo copy docker://busybox:latest oci:busybox:latest
$ oci-create-runtime-bundle busybox /tmp/myapp
$ umoci unpack --image busybox:latest /tmp/myapp
```

Or you can start with just a directory that has a root filesystem already in it:

```
$ ls /tmp/myapp/rootfs
bin      etc      lib      linuxrc  mnt      proc     run      sys      usr
dev      home     lib64    media    opt      root     sbin     tmp      var
```

In the parent directory, create an [OCI runtime configuration file][oci-runtime], or let runC generate one for you.

```
$ cd /tmp/myapp
$ runc spec
$ ls
config.json  rootfs
```

Edit the `config.json` to your liking, to specify the commands you would like to run, or any other options.
You can now run a container with runC.

```
$ runc run container-name
sh-4.4#
```

runC also supports the concept of creating and starting a container as separate operations.

```
$ runc create container-name
$ # Do some further set up.
$ runc start container-name
```

[oci-image]: https://github.com/opencontainers/image-spec
[oci-runtime]: https://github.com/opencontainers/runtime-spec
[oci-image-tools]: https://github.com/opencontainers/image-tools
[skopeo]: https://github.com/projectatomic/skopeo
[umoci]: https://github.com/cyphar/umoci
