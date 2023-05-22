```bash
# Windows 10 Lab Machine
xfreerdp /u:admin /p:lab /v:192.168.231.10 /smart-sizing:1920x1080
```

```bash
# Connect to a FreeRDP server:
xfreerdp /u:username /p:password /v:ip_address

# Connect to a FreeRDP server and activate audio output redirection using `sys:alsa` device:
xfreerdp /u:username /p:password /v:ip_address /sound:sys:alsa

# Connect to a FreeRDP server with dynamic resolution:
xfreerdp /v:ip_address /u:username /p:password /dynamic-resolution

# Connect to a FreeRDP server with clipboard redirection:
xfreerdp /v:ip_address /u:username /p:password +clipboard

# Connect to a FreeRDP server ignoring any certificate checks:
xfreerdp /v:ip_address /u:username /p:password /cert:ignore
```
