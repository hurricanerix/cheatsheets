# Fullstack

`npm` vs `npx`: Use `npx` (node package execute) if you want to execute a script once, it won't be installed to your `node_modules` directory.

```Shell
$ npx jsonlint package.json
```

## Node

Initialize module or project

```Shell
$ npm init
```

Install a specific version of a package.

```Shell
$ npm install express@4.18.2
```

Install a package as a dev dependency.

```Shell
$ npm install --save-dev karma@5.0.0
```

Audit and Fix vulnerabilities

```Shell
$ npm audit fix
$ npm audit fix --force
```

Inspects local package.json and compares it to the local node_modules directory, removing any unnecessary packages.

```Shell
$ npm prune
```

Update all installed packages to their latest acceptable versions.

```Shell
$ npm update
```

Remove a dependency.

```Shell
$ npm uninstall karma
```

Install all dependencies

```Shell
$ npm install
```
