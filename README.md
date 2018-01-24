# vagrant_redmine

## Table of Contents

1. [Description](#description)
2. [Start from beginning](#start-from-beginning)

## Description

This project allows you faster run locally Redmine.

* OS CentOS 7
* Ruby 2.3.3
* Redmine 3.4.4

You can change Redmine version and Ruby version in `playbook.yml` 

## Start from beginning

**1) [Install Vagrant](https://www.vagrantup.com/downloads.html)**

**2) [Install VirtualBox](https://www.virtualbox.org/wiki/Downloads)**

**3) Install Vagrant plugin for VirtualBox**

`# vagrant plugin installvagrant-vbguest`

**4) Add CentOS 7 image for VirtualBox**

`# vagrant box add centos/7`

**5) Clone project**

`# git clone https://github.com/noshutdown-ru/vagrant_redmine.git`

**6) Generate new key**

```
# cd ./vagrant_redmine
# ssh-keygen -f vagrant
```

**7) Start VM**

`# vagrant up `

**8) Login to VM**

`# vagrant ssh`

**9) Show public IP**

`# ip a show dev eth1`

From this ip Redmine would be available.

**10) Start Redmine**

```
# sudo -s
# cd /opt/redmine
# bundle exec rails server webrick -e production -b 0.0.0.0 -p 80
```

**11) Open in browser**
