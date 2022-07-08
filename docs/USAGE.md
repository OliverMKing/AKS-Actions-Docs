# Usage

This page contains strong examples for how to use our actions but is not supposed to be a comprehensive list of possibilities. Our actions all have configuration options that can't be completely document here. You should view each action's repository for complete action-specific documentation. There's a complete list of our actions [here](../README.md#actions).

Use these examples to learn and modify the techniques to fit your needs.

## Referencing an Action

When using our actions you will reference them by either a tag or sha.

The sha method is considered the [most secure](https://docs.github.com/en/actions/security-guides/security-hardening-for-github-actions#using-third-party-actions).

Alternatively, you can use our tags. For the newer versions we provide a major and minor version tag. If you reference an action by its major version (ex: v4, v3, v2) then it will point to the latest release on that version. More specific releases (ex: v3.1, v4.5, v2.3) can also be used and the commit they point to will never be changed.

You should use [Dependabot to subscribe to new releases](https://docs.github.com/en/code-security/dependabot/working-with-dependabot/keeping-your-actions-up-to-date-with-dependabot) since we are constantly improving our actions.

## Examples

The below examples all involve deploying to an AKS cluster. You can also use our workflows for integration tests, other k8s clusters, and logging.

### Starter Templates

The starter workflows provide the simplest examples. You can easily adopt them with these [steps](https://docs.github.com/en/actions/using-workflows/using-starter-workflows#using-starter-workflows).

- [Azure Kubernetes Service (Basic)](https://github.com/actions/starter-workflows/blob/main/deployments/azure-kubernetes-service.yml)
- [Azure Kubernetes Service Helm](https://github.com/actions/starter-workflows/blob/main/deployments/azure-kubernetes-service-helm.yml)
- [Azure Kubernetes Service Kustomize](https://github.com/actions/starter-workflows/blob/main/deployments/azure-kubernetes-service-kustomize.yml)
- [Azure Kubernetes Service Kompose](https://github.com/actions/starter-workflows/blob/main/deployments/azure-kubernetes-service-kompose.yml)

### No Image Pull Secret

Our starter templates examples. Create image pull secrets to pull down images. You don't need to do this if your container registry is [attached](https://docs.microsoft.com/en-us/azure/aks/cluster-container-registry-integration) to the cluster (or public).

[example](../examples/noimagepull.yaml)

### Promote / Reject

We can use [environments](https://docs.github.com/en/actions/deployment/targeting-different-environments/using-environments-for-deployment) to handle the [multi option](https://docs.github.com/en/actions/managing-workflow-runs/reviewing-deployments) nature of blue-green and canary deployments. A required approval will be prompted to make a decision when it reaches that stage.

[example](https://github.com/Azure-Samples/aks-bluegreen-canary)
