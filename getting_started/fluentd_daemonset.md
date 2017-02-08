# Fluentd DaemonSet

For [Kubernetes](https://kubernetes.io), a [DaemonSet](https://kubernetes.io/docs/admin/daemons/) ensures that all (or some) nodes run a copy of a _pod_. In order to solve log collection we are going to implement a Fluentd DaemonSet.

Fluentd is flexible enough and have the proper plugins to distribute logs to different third party applications like databases or cloud services, so the principal question is to know: _where the logs will be stored ?_. Once we got that question answered, we can move forward configuring our DaemonSet.

The below steps will focus on sending the logs to a Elasticsearch Pod.

> In the next updates, we will be extending the documentation with instructions to use Fluentd with different backends.

## Get Fluentd DaemonSet sources

We have created a Fluentd DaemonSet that have the proper rules and container image ready to get started:

https://github.com/fluent/fluentd-kubernetes-daemonset

Please grab a copy of the repository from the command line using GIT:

```
$ git clone https://github.com/fluent/fluentd-kubernetes-daemonset
```

## DaemonSet Content

The cloned repository contains the configuration that allows to deploy Fluentd as a DaemonSet, the Docker container image distributed on the repository also comes pre-configured so Fluentd can gather all logs from the Kubernetes node environment and also it appends the proper metadata to the logs.
