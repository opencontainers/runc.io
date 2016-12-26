+++
date = "2016-12-26T16:20:00+11:00"
title = "Extra"
include = "extra"
+++

## Systemd Integration

runC does not create a daemon, so it integrates well with systemd.

```
[Unit]
Description=Minecraft Build Server
Documentation=http://minecraft.net
After=network.target

[Service]
CPUQuota=200%
MemoryLimit=1536M
ExecStart=/usr/local/bin/runc run minecraft
Restart=on-failure
WorkingDirectory=/containers/minecraftbuild

[Install]
WantedBy=multi-user.target
```
