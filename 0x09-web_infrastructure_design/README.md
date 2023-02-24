# Web infrastructure design

<img src=https://camo.githubusercontent.com/4c26ac1a867bdf5dbcba518c034a552a7ed00bc974c27e69333505e4e8147f85/68747470733a2f2f6d656469612e6765656b73666f726765656b732e6f72672f77702d636f6e74656e742f75706c6f6164732f32303232303831373138323635312f4e6574776f726b496e667261737472756374757265312e706e67>

Web Applications Infrastructure/Web Infrastructure also called internet infrastructure is the physical hardware, transmission media, and software used to interconnect computers and users on the Internet.

- Simple Web Infrastructure
- Distributed Web Infrastructure
- Monitored Web Infrastructure

## Learning Objectives

- You must be able to draw a diagram covering the web stack you built with the *sysadmin/devops* track projects
- You must be able to explain what each component is doing
- You must be able to explain system redundancy
- Know all the mentioned acronyms: LAMP, SPOF, QPS

## Simple Web Infrastructure
<img src=https://camo.githubusercontent.com/035053570ba88a0e0de998e4e85a636681c3b1a48a47aef24e4d100ead1f54fa/68747470733a2f2f6d69726f2e6d656469756d2e636f6d2f6d61782f3732302f312a784b64314363685361534b5638334f697a6a75386b672e77656270>

- 1 server
- 1 web server (Nginx)
- 1 application server
- 1 application files (your code base)
- 1 database (MySQL)
- 1 domain name foobar.com configured with a www record that points to your server IP 8.8.8.8

## Distrubuted Web Infrastructure

- 2 servers
- 1 web server (Nginx)
- 1 application server
- 1 load-balancer (HAproxy)
- 1 set of application files (your code base)
- 1 database (MySQL)

## Monitored web infrastructure

<img src=https://camo.githubusercontent.com/c03d08e31e06481c90b3f2bda47f1eac6d0102268ca509a1545e17a459b96b96/68747470733a2f2f6d69726f2e6d656469756d2e636f6d2f6d61782f3732302f312a74376f53415756376774702d5753524e58664d3948772e77656270>

- 3 firewalls
- 1 SSL certificate to serve www.foobar.com over HTTPS
- 3 monitoring clients (data collector for Sumologic or other monitoring services)
