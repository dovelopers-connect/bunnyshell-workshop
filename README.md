# Definitions

Kubernetes is a tool that allows you to [run](https://kubernetes.io/docs/reference/generated/kubectl/kubectl-commands#run) workloads in a cluster of computers called nodes. It automates deployment, scaling and management of containerized applications \[1].

Workloads are abstracted as [Pods](https://kubernetes.io/docs/concepts/workloads/pods/), the most atomical element of the Kubernetes architecture, that can group one or more containers.

Objects in Kubernetes are typically described in yaml files. Each object has the required properties `apiVersion`, `kind`, `metadata` and `spec` \[2].

\[1] [https://kubernetes.io/](https://kubernetes.io/)

\[2] [https://kubernetes.io/docs/concepts/overview/working-with-objects/kubernetes-objects/#required-fields](https://kubernetes.io/docs/concepts/overview/working-with-objects/kubernetes-objects/#required-fields)
