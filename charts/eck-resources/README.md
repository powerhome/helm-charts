# eck-resources-chart
Helm chart for easily templating ECK resources for deploying Elasticsearch, Kibana etc with reduced duplication.

It allows the user to create some of the custom resources managed by ECK in a simpler way by taking advantage of Helm templating.

For now the chart can create the following resources:
* Elasticsearch
* Kibana
* Ingress (for kibana)
* Beats

## Depencies
This charts expects that the [ECK](https://github.com/elastic/cloud-on-k8s) is already installed and configured in the Kube cluster.

## Configuration
Each variable has a comment to what is can be used for in the [values.yaml](./values.yaml).

Besides that there are some example files in [examples/](./examples/).

## Configure OIDC
This chart allows you to configure login using OIDC. Note that this feature isn't available in the basic license.

## References
We used some of the best practices for helm charts used in  https://github.com/prometheus-community/helm-charts/tree/main/charts/kube-prometheus-stack/
