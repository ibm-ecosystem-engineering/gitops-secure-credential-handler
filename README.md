# Continuous Deployment with Argo CD & IBM Key Protect

This repository contains a sample gitops application, to help you configure Continuous Delivery (CD) using GitOps and  Application Secret using Key Protect Plugin in ArgoCD. 

### Problem:

Continues Delivery need secrets for deploying the application. Secrets with sensitive information cannot be put in Git where it is exposed.

### Solution: 

To solve the above problem, secrets can be stored in key protect and retrieved by argocd during CD. ArgoCD will fetch secrets from IBM Key Protect and deploy the application in a testing environment.

- This gitops repository is used by ArgoCD to get inputs for continous deployment whenever there is a change to the source application

- A configuration contains secrets which are needed and ArgoCD retreives them dynamically from Keyprotect and creates them in the target environment.

Argo CD follows the GitOps pattern of using Git repositories as the source of truth for defining the desired application state. Kubernetes manifests can be specified in several ways:

1. [kustomize](https://kustomize.io/) applications
2. [helm](https://helm.sh/) charts
5. Plain directory of YAML/json manifests
6. Any custom config management tool configured as a config management plugin

Argo CD automates the deployment of the desired application states in the specified target environments. Application deployments can track updates to branches, tags, or pinned to a specific version of manifests at a Git commit. See tracking strategies for additional details about the different tracking strategies available.

## Configuration of Artifactory 

Follow these [Instructions](https://github.ibm.com/garage-catalyst/iteration-zero-ibmcloud/blob/master/docs/ARTIFACTORY.md) to configure Artifactory to act as a Helm Repository

## Configuration of Argo CD

Follow these [Instructions](https://github.ibm.com/garage-catalyst/iteration-zero-ibmcloud/blob/master/docs/ARGOCD.md) to configure Argo CD to pull helm configuration from Artifactory and manage deployment of IBM Cloud Registry images into specfic `test` namespaces or projects.

## Continous Delivery

Follow these instructions to manage the deployment of an application that has been previously deployed into the `dev` namespace using Jenkins CI.

### Deployment with Artifactory and Argo CD





### Multi App Deployment

TBD
