## Helm Charts for NetFoundry Ziti

This repository may be added to [Helm](https://helm.sh/) which is a package manager for [Kubernetes](https://kubernetes.io/). After adding this repository you may then list and install the Helm charts hosted in this repository.

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
❯ helm install ziti-host-master netfoundry/ziti-host-master
```