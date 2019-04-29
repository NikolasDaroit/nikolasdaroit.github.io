---
title: 'SCP between EC2 instance and local computer'
layout: post
tags:
  - aws
  - ' ec2'
category: 
---
## SCP between Amazon EC2 instance and local computer
- To upload a file from your laptop to Amazon instance:

```
    scp -i ~/Desktop/amazon.pem ~/path/to/file/example.txt  {username}@ec2-{255.255.255.255}.compute-1.amazonaws.com:~/destination/path/
```

- To download a file from Amazon instance to your laptop:  

```
    scp -i ~/Desktop/amazon.pem {username}@ec2-{255.255.255.255}.compute-1.amazonaws.com:/path/to/file/example.zip ~/local/destination/path/

```