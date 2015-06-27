+++
date = "2015-06-07T19:03:22-07:00"
title = "Get Started"
include = "get-started"
+++

## Getting started

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