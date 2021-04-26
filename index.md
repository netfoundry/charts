
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
NAME                            CHART VERSION   APP VERSION     DESCRIPTION                
netfoundry/ziti-host-master     0.1.0           0.19.12         A Helm chart for Kubernetes
```

## Install a chart from this repo

```bash
❯ helm install ziti-host-master netfoundry/ziti-host-master --set-file enrollmentToken=./Linux1.jwt
NAME: ziti-host-master
LAST DEPLOYED: Mon Apr 26 12:19:05 2021
NAMESPACE: default
STATUS: deployed
REVISION: 1
NOTES:
1. This daemonset does not provide an ingress configuration or server listener port, only egress from the pod to "endpoint-hosted" services for a NetFoundry network:
  export POD_NAME=$(kubectl get pods --namespace default -l "app.kubernetes.io/name=ziti-host-master,app.kubernetes.io/instance=ziti-host-master" -o jsonpath="{.items[0].metadata.name}")
```

## Update this repo

```bash
# add or update a chart named "ziti-host-master" located in the top level of this repo
helm package ./ziti-host-master && helm repo index . --debug
```

Merge changes to branch "master" and push to GitHub. GitHub Pages will rebuild the web site to publish the changes. You may verify the rebuild completed by noting the presence of your update in https://netfoundry.github.io/charts/index.yaml. Then you may use the update in Helm.

```bash
❯ helm repo update && helm search repo netfoundry --versions

Hang tight while we grab the latest from your chart repositories...
...Successfully got an update from the "netfoundry" chart repository
Update Complete. ⎈Happy Helming!⎈
NAME                            CHART VERSION   APP VERSION     DESCRIPTION                
netfoundry/ziti-host-master     0.1.1           0.19.12         A Helm chart for Kubernetes
netfoundry/ziti-host-master     0.1.0           0.19.12         A Helm chart for Kubernetes
```

## Resources

* [GitHub Source for this page](https://github.com/netfoundry/charts)
* [NetFoundry Developer Portal](https://developer.netfoundry.io/)
* [Ziti.dev](https://ziti.dev/)
* [NetFoundry Home](https://netfoundry.io/)
* [NetFoundry Console](https://nfconsole.io/)
