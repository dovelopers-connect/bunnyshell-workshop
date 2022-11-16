# Definitions

Kubernetes is a tool that allows you to [run](https://kubernetes.io/docs/reference/generated/kubectl/kubectl-commands#run) workloads in a cluster of computers called nodes. It automates deployment, scaling and management of containerized applications \[1].

Workloads are abstracted as [Pods](https://kubernetes.io/docs/concepts/workloads/pods/), the most atomical element of the Kubernetes architecture, that can group one or more containers.

Objects in Kubernetes are typically described in yaml files. Each object has the required properties `apiVersion`, `kind`, `metadata` and `spec` \[2].

While pods can be run directly on the cluster is likely that based on the workload use case one of the following resource will be used.

When a reliable and scalable application is needed [Deployment](https://kubernetes.io/docs/concepts/workloads/controllers/deployment/) and [ReplicaSet](https://kubernetes.io/docs/concepts/workloads/controllers/replicaset/) will be used to describe the state of the application and the number of replica Pods desired. A [StatefulSet](https://kubernetes.io/docs/concepts/workloads/controllers/statefulset/) is used when a stateful application is desired. A [DeamonSet](https://kubernetes.io/docs/concepts/workloads/controllers/daemonset/) will make sure a Pod with the desired spec will be available on all nodes. For workloads that need to be executed once a [Job](https://kubernetes.io/docs/concepts/workloads/controllers/job/) is defined that allows specifying the number of completions and parallelism. Finally for workloads that need to be scheduled to run at specific time intervals a [CronJob](https://kubernetes.io/docs/concepts/workloads/controllers/cron-jobs/) is defined.

\[1] [https://kubernetes.io/](https://kubernetes.io/)

\[2] [https://kubernetes.io/docs/concepts/overview/working-with-objects/kubernetes-objects/#required-fields](https://kubernetes.io/docs/concepts/overview/working-with-objects/kubernetes-objects/#required-fields)
