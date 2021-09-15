
# NetFoundry Helm Charts

This is a repository of [Helm](https://helm.sh/) charts for use with [NetFoundry](https://developer.netfoundry.io) on [Kubernetes](https://kubernetes.io/). After adding this repository to Helm you may then search and install the charts (packages) hosted in this repository.

## Add this repo to Helm

```bash
❯ helm repo add netfoundry https://netfoundry.github.io/charts/                                                                                               
"netfoundry" has been added to your repositories                         
```

## Search for available charts in this repo

```bash
❯ helm search repo netfoundry
NAME                     CHART VERSION   APP VERSION     DESCRIPTION                
netfoundry/ziti-host     0.1.0           0.19.12         A Helm chart for Kubernetes
```

## Install a chart from this repo

```bash
❯ helm install ziti-host netfoundry/ziti-host --set-file enrollmentToken=./Linux1.jwt
NAME: ziti-host
LAST DEPLOYED: Mon Apr 26 12:19:05 2021
NAMESPACE: default
STATUS: deployed
REVISION: 1
NOTES:
1. This deployment does not provide an ingress / server port, only egress from the pod to any `serverEgress` destinations you configure in a NetFoundry network e.g. https://kubernetes.default.svc:443:
  export POD_NAME=$(kubectl get pods --namespace default -l "app.kubernetes.io/name=ziti-host-master,app.kubernetes.io/instance=ziti-host-master" -o jsonpath="{.items[0].metadata.name}")
```

## Resources

* [GitHub Source for this page](https://github.com/netfoundry/charts)
* [NetFoundry Developer Portal](https://developer.netfoundry.io/)
* [Ziti.dev](https://ziti.dev/)
* [NetFoundry Home](https://netfoundry.io/)
* [NetFoundry Console](https://nfconsole.io/)
