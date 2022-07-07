# Development

We welcome development contributions from everyone.

## Prerequisites

Before developing our AKS GitHub actions you should know a few concepts.

- [TypeScript](https://www.typescriptlang.org/)
- [GitHub Actions Packages](https://github.com/actions/toolkit)

You also must have [Node.js](https://nodejs.org/en/) and NPM installed.

## Environment

You can use any environment to make contributions but it might be easiest to use our setup. We reccomend using [VS Code](https://code.visualstudio.com/) with the following extensions.

- [Prettier](https://marketplace.visualstudio.com/items?itemName=esbenp.prettier-vscode) - Formats your code. Format on save should be turned on.
- [ESLint](https://marketplace.visualstudio.com/items?itemName=dbaeumer.vscode-eslint) - Linter

## Contributing

To get started, fork the repository you are making a contribution to. Then, clone the repository locally. Create a new branch for your changes on the forked repo.

Run `npm install` to install dependencies.

Make changes to the project and add unit tests. Check that the unit tests work locally with `npm run test`. Update examples in the `README.md` if changes impact how users interact with the action. Then commit and push your changes to your remote fork.

Large changes must be tested fully using the updated version in an actual GitHub Workflow. [This](https://github.com/OliverMKing/AKS-GitHub-Actions-Demo) is a good repository to fork and test off of.

Create a pull request from your fork against the main branch of the repository and get it merged in.

## Merging / Release

A member of [@Azure/aks-atlanta](https://github.com/orgs/Azure/teams/aks-atlanta) must approve the PR and merge it in. Squash merge PRs and be sure that they have an appropriate commit title.

If the PR contains code changes, it must be released. Use the [helper GitHub actions](https://github.com/OliverMKing/javascript-release-workflow#usage) to do this. If the code is a breaking change, then use a new major version release number. If it's not, use the most recent major version as input. Changes should be well documented in the release.

A breaking change means that the action behaves functionally differently than the previous version with the same exact input (other than bugfixes). This includes things like new required inputs.

If a new major version for an action is created, our [starter workflows](https://github.com/Azure/k8s-deploy/issues/174#issuecomment-1167377782) must be updated appropriately.

## Common Issues

### Can't merge due to conflicting tags

We remap our remote tags with our release workflows. Major version tags will always point to the latest version (ex: v2 will point to v2.0 then if a v2.1 is created it will be remapped to that).

Run `git fetch --tags --force` to update local tags.

### PR tests didn't run

Ocasionally our tests don't run on a PR. You attempt to trigger them by closing then reopening a PR.
