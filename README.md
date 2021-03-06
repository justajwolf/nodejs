# Nodejs Packages

This is a repo of npm pkg, with a monorepo style, managing packages by rush.

[Rush](https://rushjs.io/) is a tool that makes life easier for JavaScript developers who build and publish many packages from a common Git repo.

## Manifest

Actively, updating...

- `body-parser-xml` : a middleware to parser xml chunk, see [(^\_^)](./packages/body-parser-xml/README.md).
- `clickhouse` : a clickhouse client for nodejs, see [(^\_^)](./packages/clickhouse/README.md).

## Initial

> To setup new repo, please refer to [[->(^\_^)<-](https://rushjs.io/pages/maintainer/setup_new_repo/)]

```bash
# install rush in global, if never use rush before.
$ npm install -g @microsoft/rush
$ npm install -g pnpm
```

## Install deps

```bash
# install all deps in repo.
$ rush install

# apply rush config into repo, when modified the folder '/common/config/rush/*' and the file 'rush.json' in root.
$ rush update

# add deps for the explicit packages, pkg-path is a subset path of repo, --dev map to devDependencies in package.json
$ cd [pkg-path]
$ rush add --caret --dev -p=[pkg-name]
$ rush update
```

## Build

```bash
# build all pkg in repo
$ rush build -v

# build explicit pkg
$ rush build -v -t [pkg-name]

# build explicit pkg
$ cd [pkg-path]
$ rushx build
```

## Test

```bash
# test all pkg in repo
$ rush test -v

# test the explicit pkg
$ rush test -v -t [pkg-name]

# test explicit pkg
$ cd [pkg-path]
$ rushx test
```

## Developer

The following is an example that rush is used in combination with vscode.

- Step 1: Install vscode workspace plugin, [Monorepo Workspace](https://marketplace.visualstudio.com/items?itemName=folke.vscode-monorepo-workspace).
- Step 2: Save a vscode workspace config in repo, like `rush.code-workspace`. About vscode workspace, [see](https://code.visualstudio.com/docs/editor/workspaces).

In Workspace, u can make the .vscode folder separating into each pkg.

## Debug

In Workspace, see the explicit pkg vscode config file, like `'[pkg-name]/.vscode/launch.json'`.

## License

The License is [MIT](LICENSE).
