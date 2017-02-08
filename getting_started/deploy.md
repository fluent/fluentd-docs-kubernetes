# Logging to Elasticsearch

## Requirements

From the fluentd-kubernetes-daemonset/ directory, find the Yaml configuration file:

- [fluentd-daemonset-elasticsearch.yaml](https://github.com/fluent/fluentd-kubernetes-daemonset/blob/master/fluentd-daemonset-elasticsearch.yaml)

As an example let's see a part of  the file content:

```yaml
apiVersion: extensions/v1beta1
kind: DaemonSet
metadata:
  name: fluentd
  namespace: kube-system
  ...
spec:
    ...
    spec:
      containers:
      - name: fluentd
        image: quay.io/fluent/fluentd-kubernetes-daemonset
        env:
          - name:  FLUENT_ELASTICSEARCH_HOST
            value: "elasticsearch-logging"
          - name:  FLUENT_ELASTICSEARCH_PORT
            value: "9200"
        ...
```

The Yaml file have two relevant environment variables that are used by Fluentd when the container starts:

| Environment Variable           | Description | Default              |
|--------------------------------|-------------|----------------------|
| FLUENT\_ELASTICSEARCH\_HOST    | Specify the host name or IP address.|elasticsearch-logging |
| FLUENT\_ELASTICSEARCH\_PORT    | Elasticsearch TCP port             | 9200                 |

Any relevant change needs to be done to the Yaml file before to deploy it. Using the default values assumes that at least an Elasticsearch Pod __elasticsearch-logging__ exists in the cluster.
