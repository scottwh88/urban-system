# Web Task

## Overview

Three servers are deployed using Vagrant and provisioned via Ansible

Two servers are Apache web servers (*web01* & *web02*) running "hello world" web application

One server is a HA Proxy Load Balancer (*lb01*) with a round robin configuration

## Prerequisite

### Minimum Requirements (built and tested with) 
* [Vagrant 2.2.0](https://www.vagrantup.com/downloads.html)
* [VirtualBox 5.2.20](https://www.virtualbox.org/wiki/Downloads)
* [Ansible 2.7.1](https://docs.ansible.com/ansible/2.7/installation_guide/intro_installation.html#installing-the-control-machine)
* macOS 10.14 (Mojave)


### Installation 

`$ git clone https://github.com/scottwh88/urban-system`

## Usage

```bash
vagrant up
```
## Servers

| Server Name | IP|Role|Operating System|
| -|:-:|-:|-:|
| web01| 192.168.33.11 |Web Server (Apache)|CentOS 7|
| web02| 192.168.33.12|Web Server (Apache)|CentOS 7|
| lb01|192.168.33.12|Load Balancer (HAProxy)|CentOS 7|

## Network Diagram

![Network Diagram](https://i.imgur.com/BFU7ANj.png)

## Ansible Roles and Configuration

1. **common** (executed on all servers)
   * Configures DNS (/etc/hosts  file)
   * Ensures the *firewalld* service is started
   * Ensures the *firewalld* service is enabled
   * Opens port 80 (http) on the *firewalld* service 

2. **web** (executed on web servers)
   * Installs *httpd* package
   * Starts *httpd* service
   * Enables *httpd* service 
   * Deploys Bootstrap web code 
   * Deploys customised index.html template (Jinja2)  

3. **lb** (deployed on load balancer)
   * Installs *haproxy* package
   * Deploys *haproxy* configuration file
   * Starts *haproxy* service
   * Enables *haproxy* service

## Demonstration (YouTube)

[![YouTube Demo](http://img.youtube.com/vi/mjUEoHenius/0.jpg)](http://www.youtube.com/watch?v=mjUEoHenius "Video Title")

## Credits

* [Bootstrap](https://getbootstrap.com/) for Web Framework used in deployment
* [Apache](https://httpd.apache.org)
* [CentOS](https://www.centos.org)
* [HAProxy](http://www.haproxy.org)
* [Vagrant](https://www.vagrantup.com)
* [Ansible](https://www.ansible.com)
* [Draw.io](https://www.draw.io)


## License
[MIT](https://choosealicense.com/licenses/mit/)