---
title: 'Bash commands'
layout: post
tags:
  - bash
category: 
---
## Bash commands

- Find all TEXT in FILES in FOLDER
```
        grep -rnw '/path/to/somewhere/' -e 'pattern'
```

- Symlink
```
        ln -s /path/original/file /path/to/link
```

- Clear NGINX log without stopping Via
```
sudo sh -c "cat /dev/null > nginx.server.access_log"
```


- Make a virtualenv with python 3 
```
mkvirtualenv --python=`which python3` nameOfEnvironment
```