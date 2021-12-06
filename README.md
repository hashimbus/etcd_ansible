# etcd_ansible
distrib UBUNTU (18 or 20)
main github: https://github.com/etcd-io/etcd

**Role etcd:**
Write /vars/distrib_version: (main github)

Install etcd as service
user: etcd
conf: /etc/etcd
data: /var/lib/etcd
service: /etc/systemd/system/etcd.service

**Role etcd_config:**
Write vars/ (etcd hostname + ip) and (ssh_addresses for allow ssh firewall )
etcd_hosts:
        - hostname: 
          ip: 
ssh_address:
        - 

Write hostname to /etc/hosts and 
enable ufw firewall, 
open 22 port(vars) and 2379:2380 (between nodes)

**Role etcd_ssh:**
Write vars/ (etcd hostname + ip) may copy from etcd_config
etcd_hosts:
        - hostname: 
          ip: 
          
Role create directory /tmp/.artifacts/ on localhost
Create and copy certs (crt+key) ca and hosts
Copy certs on hosts
(inventory_hostnames must be like match names hosts)
