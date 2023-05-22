```bash
scp [OPTION] [user@]SRC_HOST:]file1 [user@]DEST_HOST:]file2
```
-   `OPTION` - [scp options](https://linux.die.net/man/1/scp) such as cipher, ssh configuration, ssh port, limit, recursive copy …etc.
	-   `-P` - Specifies the remote host ssh port.
	-   `-p` - Preserves files modification and access times.
	-   `-q` - Use this option if you want to suppress the progress meter and non-error messages.
	-   `-C` - This option forces `scp` to compresses the data as it is sent to the destination machine.
	-   `-r` - This option tells `scp` to copy directories recursively.
-   `[user@]SRC_HOST:]file1` - Source file.
-   `[user@]DEST_HOST:]file2` - Destination file


```bash
scp -P 2222 student@192.168.210.52:/path/to/source/file /path/to/destination
```