# HTTPS SSL
<img src=https://camo.githubusercontent.com/6f2755246f0bf6a9246f5b13d9853eda143395d116be5fe93f0fe576d07e2ce4/68747470733a2f2f7777772e782d636172742e636f6d2f696d672f383532372f687474705f746f5f68747470732d312e77656270>
SSL stands for Secure Sockets Layer and, in short, it's the standard technology for keeping an internet connection secure and safeguarding any sensitive data that is being sent between two systems, preventing criminals from reading and modifying any information transferred, including potential personal details. The two systems can be a server and a client (for example, a shopping website and browser) or server to server (for example, an application with personal identifiable information or with payroll information).

HTTPS (Hyper Text Transfer Protocol Secure) appears in the URL when a website is secured by an SSL certificate. The details of the certificate, including the issuing authority and the corporate name of the website owner, can be viewed by clicking on the lock symbol on the browser bar.

What happens when you don’t secure your website traffic?
<img src=https://camo.githubusercontent.com/0668ed14a0930c94885381ea246b0b3b2e9bf836cf6068549d7bcff806802dc1/68747470733a2f2f73332e616d617a6f6e6177732e636f6d2f696e7472616e65742d70726f6a656374732d66696c65732f686f6c626572746f6e7363686f6f6c2d73797361646d696e5f6465766f70732f3237362f78436d4f4367772e676966>

## Prerequisites
- What is HTTPS?
- What are the 2 main elements that SSL is providing
- HAProxy SSL termination on Ubuntu16.04
- SSL termination
- Bash function

## Requirements
- Allowed editors: vi, vim, emacs
- All your files will be interpreted on Ubuntu 16.04 LTS
- All your files should end with a new line
- A README.md file, at the root of the folder of the project, is mandatory
- All your Bash script files must be executable
- Your Bash script must pass Shellcheck (version 0.3.7) without any error
- The first line of all your Bash scripts should be exactly #!/usr/bin/env bash
- The second line of all your Bash scripts should be a comment explaining what is the script doing

## Installing SSL Termination on Haproxy
Linux Distro: Ubuntu 20.04 LTS
HAProxy Version: v2.4.3
```

#if you already have haproxy installed do this
$ sudo snap install --classic certbot

# check if haproxy is installed, if yes stop haproxy
$ sudo service haproxy stop

# Install ssl using certbot
$ sudo certbot certonly --standalone

# Follow the instrustions accurately, at the end please take note of the
# Location of your SSL Keys. Usually going to default to the /etc/letsencrypt
# directory. To view them do the below
$ ls /etc/letsencrypt/live/domain_name/

# Now concat your certificate .pem files to a single pem file and save them to
# /etc/ssl/private
$ cat cert_key_1 cert_key_2 > /etc/ssl/private/any_desired_name.pem

# Now go to your haproxy config file to add a the path to your certificate
# Then reload haproxy
$ sudo service haproxy reload
```
