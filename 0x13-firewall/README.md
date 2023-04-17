# 0x13 Firewall

<img src=https://camo.githubusercontent.com/ed0fae49a7111eb383d042c21aad18a7b29651de3d8e8d31c2a4142cd5509e96/68747470733a2f2f7777772e636f6d7075717569702e636f6d2f68732d66732f68756266732f696d616765732f626c6f672d696d616765732f6669726577616c6c2d6d6f6e69746f72696e672d626573742d7072616374696365732e6a70673f77696474683d363030266e616d653d6669726577616c6c2d6d6f6e69746f72696e672d626573742d7072616374696365732e6a7067>

A firewall is a network security device that monitors incoming and outgoing network traffic and permits or blocks data packets based on a set of security rules. Its purpose is to establish a barrier between your internal network (LAN) and incoming traffic from external sources (such as the internet) in order to block malicious traffic like viruses and hackers.

# The UFW On Linux Distro

<img src=https://camo.githubusercontent.com/7569e12f8f02496051a5260979c7bd379efb474a07249c65c63a762e3830437b/68747470733a2f2f636f646564657369676e2e66722f77702d636f6e74656e742f75706c6f6164732f323031382f30382f7562756e74752d7566772d312d383830783237362e706e67>

The **Uncomplicated firewall (UFW)** in my ubuntu 22.04 LTS comes preinstalled but disabled, i only needed to enable it to get going. However lets take note of the following:

- Once UFW is enabled you have to set the rules on that terminal session especially when you're connecting via ssh cause by default ufw blocks all connection to port 22.
- UFW doesn't have a native port forwarding command, you need to do it via its /etc/ufw/before.rules file
- You also need to enable port forwarding by uncommenting the net.ipv4.ip_forward=1 line in /etc/sysctl.conf

## Code Instructions


### Code on Terminal

```
# check if ufw is installed or enabled
$ sudo ufw status

# if the result shows enabled then disable it
$ sudo ufw disable

# configuring firwall rules
$ sudo ufw default deny incoming
$ sudo ufw default allow outgoing
$ sudo ufw allow 22/tcp		/to enable ssh connection
$ sudo ufw allow 80/tcp		/to enable connection on port 80
$ sudo ufw allow 443/tcp	/to enable conection on port 443
$ sudo ufw enable

# enabling port forwarding via UFW

# add this below rule to the /etc/ufw/before.rules file
# make sure its before the *filter line, VERY IMPORTANT

*nat
: PREROUTING ACCEPT [0:0]
-A PREROUTING -p tcp --dport 8080 -j REDIRECT --to-port 80
COMMIT

# Then go to your /etc/sysctl.conf file to enable port forwarding by
# uncommenting the line #net.ipv4.ip_forward=1

-- before
#net.ipv4.ip_forward=1

--after
net.ipv4.ip_forward=1

# then reload the sysctl configuration
$ sudo sysctl -p

# congratulations !! you've done it
# if this is confusing, then watch the video above to get it done yourself.
```
