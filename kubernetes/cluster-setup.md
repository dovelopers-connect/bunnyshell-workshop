# Cluster setup

## Get the training resources

(password is not provided)

```bash
wget https://training.linuxfoundation.org/cm/LFD259/LFD259_V2022-02-25_SOLUTIONS.tar.xz n --user=LFtraining --password=
```

## Setup the container repository

When the cluster is restarted for some reason the tags in the container repository are lost.

This leads to pods for the simpleapp to become unailable. In order to fix it the following steps need to be performed.

Retrieve the repository catalog to confirm its empty

```bash
curl $repo/v2/_catalog
```

The output is the following json

```
{"repositories":[]}
```

Navigate in the app1 directory and tag the app

```
cd app1/
sudo podman push $repo/simpleapp
```

Check the repository again with the curl command.

The output should be the following json

```
{"repositories":["simpleapp"]}
```

Now you can redeploy the simpleapp if needed

## Check the NFS mount

