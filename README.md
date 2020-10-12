# Continuous Deployment with Argo CD & IBM Key Protect

This repository contains a number of samples to help you configure Continuous Delivery (CD) using GitOps and Configure Secret using Key Protect Plugin in ArgoCD. 

### Problem:

Ideally for continues delivery secrets need for deploying the application. Gitops repository contains secrets yaml thats cause security viloation problem.

### Solution: 

To Solve the above problem. We are creating secrets using IBM Key Protect. So the secret file not available in the Gitops repo. For Continues Delivery it will fetch secrets from IBM Key Protect and deploye the application in testing environment. 


For achieving above solution we need to create the two application in ArgoCD.

1. Deploy the application in test envrionment to configure Continuous Delivery (CD) using GitOps.
2. Deploye the application with secret configuration thats contains KeyId of IBM Key Protect and it will pull the secret from Key Protect.


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
