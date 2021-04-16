# Wordpress deployment in a scalable infrastructure

A scalable infrastructure is comprised by a web server with a load balancer and multiple instances that are provisioned in periods with high demand. In order to ensure persistence a database instance is required. Static files are stored in a network file share.

![horizontal scalable infrastructura](.gitbook/assets/webservers-horizontal-scale.png)

## Web Server



## Network file system \(nfs\)

Install NFS

```text
sudo apt-get install nfs-kernel-server
```

Create a directory

```text
sudo mkdir /nfsdata
```

Edit /etc/exports

```text
/nfsdata 10.0.0.0/8(rw,sync,no_subtree_check)
```

Export share

```text
sudo exportfs -rav
```

## Pricing

| Component | Monthly price |
| :--- | :--- |
| Load balancer | $10 |
| Instances  | $30 |
| Storage | $10 |
| Persistance | $20 |
| Bunnyshell | $49 |
| **Total** | $110 |

