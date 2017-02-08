# Kubernetes Logging with Fluentd

![](imgs/fluentd_kubernetes.png)

[Kubernetes](http://kubernetes.io) provides two logging end-points for applications and cluster logs: Stackdriver Logging for use with Google Cloud Platform and Elasticsearch. Behind the scenes there is a logging agent that take cares of log collection, parsing and distribution: [Fluentd](http://www.fluentd.org).

The following document focus on how to deploy Fluentd in Kubernetes and extend the possibilities to have different destinations for your logs.
