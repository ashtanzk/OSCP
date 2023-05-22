# Python 2
```bash
python -m SimpleHTTPServer <PORT>
# hosts files from current working directory
```

# Python 3
```bash
python3 -m http.server <PORT>
# hosts files from current working directory
```

# PHP
```bash
php -S 0.0.0.0:<PORT>
```

# Ruby
```bash
ruby -run -e httpd . -p <PORT>
# hosts files from current working directory
```

# Busybox
```bash
busybox httpd -f -p <PORT>
```