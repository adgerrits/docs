# Getting Started

The CNO platform can be deployed on your local host and in a datacenter.

This document gets you started.

# Pre-requisites for deployment on local host

The following components are assumed to be present on your local host (development machine):

- [Docker daemon](https://docs.docker.com/get-docker/)
- [Kubectl commandline](https://kubernetes.io/docs/tasks/tools/install-kubectl/)
- [Kind](https://kind.sigs.k8s.io/docs/user/quick-start/), [Minikube](https://kubernetes.io/docs/tasks/tools/), [Docker Desktop](https://www.docker.com/products/docker-desktop) or equivalent Kubernetes cluster

For Kubernetes cluster on local host:

- Avoid installing the default ingress controller (e.g. avoid the [Kind- ](https://kind.sigs.k8s.io/docs/user/ingress/#setting-up-an-ingress-controller) or [Minikube default](https://kubernetes.io/docs/tasks/access-application-cluster/ingress-minikube/)), as it will be added as CNO component later on.
- When using Kind, consider applying [one master with three worker nodes](./examples/kind_1m3w.yaml), to mimic a "real" cluster in the datacenter. The nodes have given names, this faciliates running some of the CNO examples later on:
```
kind create cluster --config $PWD/examples/kind_1m3w.yaml
```

Note that it is also possible to deploy from local host to a cluster in the (public) cloud.

# Deploy CNO platform

Deploy the CNO platform using mandatory- and optional components.

*[All components](https://gitlab.com/logius/cloud-native-overheid/components) will gradually be added to the below table whilst standardizing on documentation.*

## Mandatory components

Deploy in the following order:

| **Component**                                                                                 | **Purpose**                                     |
| --------------------------------------------------------------------------------------------- | ----------------------------------------------- |
| [platform-runner](https://gitlab.com/logius/cloud-native-overheid/components/platform-runner) | Tooling to deploy all other CNO components      |
| [bootstrap](https://gitlab.com/logius/cloud-native-overheid/components/bootstrap)             | Bootstrap (only for datacenter, skip for local) |
| [echo-service](https://gitlab.com/logius/cloud-native-overheid/components/echoservice)        | Hello world example (optional)                  |
| [certmanager](https://gitlab.com/logius/cloud-native-overheid/components/certmanager)         | Let's encrypt certificate automation            |
| [prometheus](https://gitlab.com/logius/cloud-native-overheid/components/prometheus)           | Only the Prometheus CRDs at this stage          |
| [nginx-ingress](https://gitlab.com/logius/cloud-native-overheid/components/nginx-ingress)     | Ingress controller (using the Prometheus CRDs)  |
| [keycloak](https://gitlab.com/logius/cloud-native-overheid/components/keycloak)               | Identity and Access Management (IAM)            |

## Optional components

Deploy arbitrarily:

| **Component**                                                             | **Purpose**         |
| ------------------------------------------------------------------------- | ------------------- |
| [nexus](https://gitlab.com/logius/cloud-native-overheid/components/nexus) | Artifact management |
