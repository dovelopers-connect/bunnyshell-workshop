# Wordpress deployment in a scalable infrastructure

A scalable infrastructure is comprised by a web server with a load balancer and multiple instances that are provisioned in periods with high demand. In order to ensure persistence a database instance is required. Static files are stored in a network file share.

![horizontal scalable infrastructura](./images/webservers-horizontal-scale.png)

## Network file system (nfs)

Install NFS

```
sudo apt-get install nfs-kernel-server
```

Create a directory

```
sudo mkdir /nfsdata
```

Edit /etc/exports 

```
/nfsdata 10.0.0.0/8(rw,sync,no_subtree_check)
```

Export share

```
sudo exportfs -rav
```