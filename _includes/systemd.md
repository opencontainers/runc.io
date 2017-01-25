## Systemd Integration

runC does not create a daemon, so it integrates well with systemd.

```systemd
[Unit]
Description=Minecraft Build Server
Documentation=http://minecraft.net
After=network.target

[Service]
Type=forking
ExecStart=/usr/local/sbin/runc run -d --pid-file /run/minecraft.pid minecraft-build-container
ExecStopPost=/usr/local/sbin/runc delete minecraft-build-container
WorkingDirectory=/opt/minecraft
PIDFile=/run/minecraft.pid

[Install]
WantedBy=multi-user.target
```
