+++
date = "2015-06-07T19:03:22-07:00"
title = "Extra"
include = "extra"
+++

## Systemd Integration

runC does not create a dameon, so it integrates well with systemd.

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
