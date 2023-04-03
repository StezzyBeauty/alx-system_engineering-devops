# Load balancer

<img src=https://camo.githubusercontent.com/48a039f1c432f831ce5d3fd4f86007f0310ead0f024ecf3b356c6f4ad890f20c/68747470733a2f2f6d69726f2e6d656469756d2e636f6d2f6d61782f3732302f302a43434b31354f463344697a6d4f49546b>

Let’s improve our web stack so that there is redundancy for our web servers. This will allow us to be able to accept more traffic by doubling the number of web servers, and to make our infrastructure more reliable. If one web server fails, we will still have a second one to handle requests.

For this project, you will need to write Bash scripts to automate your work. All scripts must be designed to configure a brand new Ubuntu server to match the task requirements.

## Concepts
- HTTP Header
- Debian/UbuntuHAProxy Packages
- Introduction to Load Balancing.

## Requirements
- Allowed editors: vi, vim, emacs
- All your files will be interpreted on Ubuntu 16.04 LTS
- All your files should end with a new line
- A README.md file, at the root of the folder of the project, is mandatory
- All your Bash script files must be executable
- Your Bash script must pass Shellcheck (version 0.3.7) without any error
- The first line of all your Bash scripts should be exactly #!/usr/bin/env bash
- The second line of all your Bash scripts should be a comment explaining what is the script doing.

## Installing HAProxy and configuring HAProxy

```

$ sudo apt-get install -y haproxy=1.6.\*

$ sudo vi /etc/haproxy/haproxy.cfg
# Add the below code to the file opened using vi editor
frontend sammykingx.tech
        bind 0:80
	mode http
        default_backend web_servers

backend web_servers
        balance roundrobin
        server 64820-web-01 100.26.152.157:80
        server 64820-web-02 52.86.102.6:80
~
~
:wq(to save and exit)
--------------- or ----------------------- 
$ echo '
frontend sammykingx.tech
        bind 0:80
	mode http
        default_backend web_servers

backend web_servers
        balance roundrobin
        server 64820-web-01 100.26.152.157:80
        server 64820-web-02 52.86.102.6:80
' >> /etc/haproxy/haproxy.cfg

$ service haproxy restart

# git clone this repo on your terminal and run the file
# install_haproxy_safely or 1-install_load_balancer to 
# configure yours on a fly.
```
