+++
date = "2016-12-26T15:00:00+11:00"
title = "About runC"
include = "home"
+++

## About runC

runC is a CLI tool for spawning and running containers according to the OCI specification.
The code can be found on <a href="https://github.com/opencontainers/runc">Github</a>.

### Embeddable
Containers are started as a child process of runC and can be embedded into various other systems without having to run a daemon.

### Battle Hardened
runC is built on libcontainer, the same container technology powering millions of Docker Engine installations.

### Unopinionated
runC does not force you to have a particular workflow or deployment setup, it only requires a root filesystem and configuration.
