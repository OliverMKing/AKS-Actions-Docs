# Azure Kubernetes Service GitHub Action Docs

Our AKS GitHub actions allow CI/CD pipelines to be easily setup for Kubernetes clusters. The Actions are compatable with any K8S cluster (not limited to Azure or AKS).

## Actions

- [azure/aks-set-context](https://github.com/Azure/aks-set-context)
- [azure/k8s-set-context](https://github.com/Azure/k8s-set-context)
- [azure/k8s-bake](https://github.com/Azure/k8s-bake)
- [azure/k8s-create-secret](https://github.com/Azure/k8s-create-secret)
- [azure/k8s-deploy](https://github.com/Azure/k8s-deploy)
- [azure/k8s-lint](https://github.com/Azure/k8s-lint)
- [azure/setup-helm](https://github.com/Azure/setup-helm)
- [azure/setup-kubectl](https://github.com/Azure/setup-kubectl)
- [azure/k8s-artifact-substitute](https://github.com/Azure/k8s-artifact-substitute)
- [azure/aks-create-action](https://github.com/Azure/aks-create-action)

## Using Actions

For basic examples of how our actions are used check out our azure-kubernetes-service [starter workflows](https://github.com/actions/starter-workflows/tree/main/deployments) ([basic](https://github.com/actions/starter-workflows/blob/main/deployments/azure-kubernetes-service.yml), [helm](https://github.com/actions/starter-workflows/blob/main/deployments/azure-kubernetes-service-helm.yml), [kompose](https://github.com/actions/starter-workflows/blob/main/deployments/azure-kubernetes-service-kompose.yml), [kustomize](https://github.com/actions/starter-workflows/blob/main/deployments/azure-kubernetes-service-kustomize.yml)). Read through them first then check out our examples in this repo.

For more options, visit the README's for each action. There are lots of configuration options for each action to fit your needs.

## Contributing

### Prerequisites

Before working with or contributing to our AKS GitHub actions you should know a few concepts. Visit the links below for documentation.

- [GitHub Actions](https://docs.github.com/en/actions)
- [TypeScript](https://www.typescriptlang.org/)
- [GitHub Actions Packages](https://github.com/actions/toolkit)

You also must have [Node.js](https://nodejs.org/en/) and NPM installed.

#### Contributing Environment

You can use any environment to make contributions but it might be easier to use our setup. We reccomend using [VS Code](https://code.visualstudio.com/) with the following extensions.

- [Prettier](https://marketplace.visualstudio.com/items?itemName=esbenp.prettier-vscode) - Formats your code. Format on save should be turned on.
- [ESLint](https://marketplace.visualstudio.com/items?itemName=dbaeumer.vscode-eslint) - Linter

### Contributions

We welcome contributions from everyone. To get started, fork the repository you are making a contribution to. Then, clone the repository locally. After the repository is local, create a new branch for your changes.

Run `npm install` to install dependencies the project needs.

Make the changes to the project and add unit tests testing your changes. Check that the unit tests work locally with `npm run test`. Update examples in the `README.md` if changes impact how users interact with the action. Then commit and push your changes to your remote fork.

For large changes, actions should be tested fully by using the updated version in an actual GitHub Workflow. [This](https://github.com/OliverMKing/AKS-GitHub-Actions-Demo) is a good repository to fork and test off of.

Create a pull request from your fork against the main branch of the repository and get it merged in.

### Merging / Release

A member of [@Azure/aks-atlanta](https://github.com/orgs/Azure/teams/aks-atlanta) must approve the PR and merge it in. Squash merge PRs and be sure that they have an appropriate commit title.

If the PR contains code changes, it must be released. Use the [helper GitHub actions](https://github.com/OliverMKing/javascript-release-workflow#usage) to do this. If the code is a breaking change, then use a new major version release number. If it's not, use the most recent major version as input. Changes should be well documented in the release.

A breaking change means that the action behaves functionally differently than the previous version with the same exact input (other than bugfixes). This includes things like new required inputs.

If a new major version for an action is created, our [starter workflows](https://github.com/Azure/k8s-deploy/issues/174#issuecomment-1167377782) must be updated appropriately.

## Common issues

### Can't merge due to conflicting tags

We remap our remote tags with our release workflows. Major version tags will always point to the latest version (ex: v2 will point to v2.0 then if a v2.1 is created it will be remapped to that).

Run `git fetch --tags --force` to update local tags.

### PR tests didn't run

Ocasionally our tests don't run on a PR. You attempt to trigger them by closing then reopenig a PR.
