# 0X0C - Web Server

<img src=https://camo.githubusercontent.com/b6daf96d50fedecd838ad587a8bec1b30475cdd61044a07a0a1d1091b0d6bc49/68747470733a2f2f7777772e6b65696c2e636f6d2f7061636b2f646f632f6d772f4e6574776f726b2f68746d6c2f687474705f7365727665725f626c6f636b5f6469616772616d2e706e67>
Web servers consist of hardware and software that use Hypertext Transfer Protocol (HTTP) to respond to web users’ requests made via the World Wide Web.

**NOTE:** In this project, some of the tasks will be graded on 2 aspects:

- Is your web-01 server configured according to requirements
- Does your answer file contain a Bash script that automatically performs commands to configure an Ubuntu machine to fit requirements (meaning without any human intervention).

## Learning Objectives
A good software engineer is a lazy software engineer, crazy right.
<img src=https://camo.githubusercontent.com/ff1d3410c1d41f82325c34f932efcd5cbd51a45b4be1b46e6d59eef80b56dfe4/68747470733a2f2f73332e616d617a6f6e6177732e636f6d2f696e7472616e65742d70726f6a656374732d66696c65732f686f6c626572746f6e7363686f6f6c2d73797361646d696e5f6465766f70732f3236362f383256735945432e6a7067>

**General Objectives** - what is the main role of a web server - What is a child process - Why web servers usually have a parent process and child processes - What are the main HTTP requests

**DNS** - What DNS stands for - What is DNS main role

**DNS** Record Types - A Records - CNAME - TXT Records - MX Records
- How the web works
- Nginx
- How to Configure Nginx
- Child process concept page
- Root and sub domain
- HTTP requests
- HTTP redirection
- Not found HTTP response code
- Logs files on Linux
- HTTP/1.1 and HTTP/2
- scp and curl

## Requirements
General

- Allowed editors: vi, vim, emacs
- All your files will be interpreted on Ubuntu 16.04 LTS
- All your files should end with a new line
- A README.md file, at the root of the folder of the project, is mandatory
- All your Bash script files must be executable
- Your Bash script must pass Shellcheck (version 0.3.7) without any error
- The first line of all your Bash scripts should be exactly #!/usr/bin/env bash
- The second line of all your Bash scripts should be a comment explaining what is the script doing
- You can’t use systemctl for restarting a process
- A prior knowledge to bash scripting

## Installing Needed Packages
```

$ sudo apt-get install shellcheck -y

# Check shellcheck version

$ shellcheck -V

# Installing nginx

$ sudo apt-get install nginx -y
```

## Configuring nginx
```

# Configuring the default file

$ sudo vi /etc/nginx/sites-available/default

# Once the vi editior opens

server {
  listen 80 default_Server;
  root /var/www/html;
  index index.html index.htm index.nginx-debian.html;

# if you have a domain name replace '_' with it
  server_name _;

# configuring error_page
  error_page 404 404.html;

  location / {
	try_files $uri $uri/ =404;
  }

  location = /404.html {
	internal;
  }
}
```
