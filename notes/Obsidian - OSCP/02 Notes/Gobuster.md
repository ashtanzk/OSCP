Used to scan websites for directory discovery, to look for optimal locations to upload web shells.

```bash
sudo apt-get update
sudo apt-get install gobuster
```

Wordlists located at `/usr/share/wordlists/dirbuster`

```bash
gobuster dir -u http://10.10.78.157:3333 -w <word-list-location>
```
