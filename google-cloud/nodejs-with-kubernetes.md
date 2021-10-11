# NodeJS with Kubernetes

[https://www.cloudskillsboost.google/focuses/564](https://www.cloudskillsboost.google/focuses/564)

```bash
gcloud auth list
gcloud config list project
nano server.js
node server.js
nano Dockerfile
docker build -t gcr.io/qwiklabs-gcp-02-fc2d3b0e5376/hello-node:v1 .
docker run -d -p 8080:8080 gcr.io/qwiklabs-gcp-02-fc2d3b0e5376/hello-node:v1
curl http://localhost:8080
docker ps
docker stop 8c3
gcloud auth configure-docker
docker push gcr.io/qwiklabs-gcp-02-fc2d3b0e5376/hello-node:v1
gcloud config set project qwiklabs-gcp-02-fc2d3b0e5376
gcloud container clusters create hello-world --num-nodes 2--machine-type n1-standard-1 --zone us-central1-a
gcloud container clusters create hello-world --num-nodes 2 --machine-type n1-standard-1 --zone us-central1-a
kubectl create deployment hello-node --image gcr.io/qwiklabs-gcp-02-fc2d3b0e5376/hello-node:v1
kubectl get deployments
kubectl get pods
kubectl cluster-info
kubectl config view
kubectl get events
kubectl expose deployment hello-node --type="LoadBalancer" --port=8080
kubectl get services
kubectl get deployment
kubectl scale deployment hello-node --replicas=4
kubectl get deployment
kubectl get pods
kubectl get deployment
kubectl get pods
```
