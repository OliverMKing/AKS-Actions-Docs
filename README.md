# AKS-Actions-Docs

## Owned Actions

- [azure/aks-set-context](https://github.com/Azure/aks-set-context)
- [azure/k8s-set-context](https://github.com/Azure/k8s-set-context)
- [azure/k8s-bake](https://github.com/Azure/k8s-bake)
- [azure/k8s-create-secret](https://github.com/Azure/k8s-create-secret)
- [azure/k8s-deploy](https://github.com/Azure/k8s-deploy)
- [azure/k8s-lint](https://github.com/Azure/k8s-lint)
- [azure/setup-helm](https://github.com/Azure/setup-helm)
- [azure/setup-kubectl](https://github.com/Azure/setup-kubectl)
- [azure/aks-create-action](https://github.com/Azure/aks-create-action)

## Contributing 

### Prerequisites

Before working with our contributing to our AKS GitHub actions you should know a few concepts. Visit the links below for documentation.

- [GitHub Actions](https://docs.github.com/en/actions)
- [TypeScript](https://www.typescriptlang.org/)

You also must have [Node.js](https://nodejs.org/en/) and NPM installed.

### Contributions

First, fork the repository you are making a contribution to. Then, clone the repository locally. After the repository is local, create a new branch for your changes.

Run `npm install` to install dependencies the project needs. 

Make the changes to the project and add unit tests testing your changes. Make sure the unit tests work locally with `npm run test`. Then commit and push your changes to your remote fork.

Create a pull request from your fork against the main branch of the repository and get it merged in.

### Merging / Release

A member of @Azure/aks-atlanta must approve the PR and merge it in. If the PR contains code changes, it must be released. Use the [helper GitHub actions](https://github.com/OliverMKing/javascript-release-workflow#usage) to do this. If the code is a breaking change, then use a new major version release number. If it's not, use the most recent major version as input. Changes should be well documented in the release.

A breaking change means that the action behaves functionally differently than the previous version with the same exact input (other than bugfixes). This includes things like new required inputs.

