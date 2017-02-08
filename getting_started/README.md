# Getting Started

The following document assumes that you have a Kubernetes cluster running or at least a local (single) node that can be used for testing purposes.

Before to get started, make sure you understand or have a basic idea about the following concepts from Kubernetes:

- [Node](https://kubernetes.io/docs/admin/node/)
>A node is a worker machine in Kubernetes, previously known as a minion. A node may be a VM or physical machine, depending on the cluster. Each node has the services necessary to run pods and is managed by the master components...
- [Pod](https://kubernetes.io/docs/user-guide/pods/)
>A pod (as in a pod of whales or pea pod) is a group of one or more containers (such as Docker containers), the shared storage for those containers, and options about how to run the containers. Pods are always co-located and co-scheduled, and run in a shared context...
- [DaemonSet](https://kubernetes.io/docs/admin/daemons/)
>A DaemonSet ensures that all (or some) nodes run a copy of a pod. As nodes are added to the cluster, pods are added to them. As nodes are removed from the cluster, those pods are garbage collected. Deleting a DaemonSet will clean up the pods it created...

Since applications runs in Pods and multiple Pods might exists across multiple nodes, we need a specific Fluentd-Pod that takes care of log collection on each node: [Fluentd DaemonSet](fluentd_daemonset.md).
