# New Module Starter
![Node.js CI](https://github.com/nodeshift/new-module-starter/workflows/Node.js%20CI/badge.svg)
[![Coverage Status](https://coveralls.io/repos/github/nodeshift/new-module-starter/badge.svg?branch=main)](https://coveralls.io/github/nodeshift/new-module-starter?branch=main)

This repo is for reference when creating a new node module/application in the nodeshift org.

## Minimum requirements

### Commit Messages

We have been trying to adhere to conventional commits, https://www.conventionalcommits.org/en/v1.0.0/, which helps when creating our changelogs and releases.

We also try to stay away from merge commits to keep the git history clean.

npm >= 7

```
npm install standard-version -D
npm set-script release "standard-version"
```

npm < 7

```
npm install standard-version -D
```

Add to package.json
```
 "scripts": {
    "release": "standard-version",
```

We can run this with `--dry-run` option to see the results, for example:

```
$ npm run release -- --dry-run

> npcheck@0.1.13 release /home/lm/code/npcheck
> standard-version "--dry-run"

✔ bumping version in package.json from 0.1.13 to 0.1.14
✔ bumping version in package-lock.json from 0.1.13 to 0.1.14
✔ created CHANGELOG.md
✔ outputting changes to CHANGELOG.md

---
### 0.1.14 (2021-07-06)


### Features

* adding initial test structure ([#4](https://github.com/nodeshift/npcheck/issues/4)) ([e6281df](https://github.com/nodeshift/npcheck/commit/e6281df6e803ced9c6d57460821af7d8a431480e))
---

✔ committing package-lock.json and package.json and CHANGELOG.md
✔ tagging release v0.1.14
ℹ Run `git push --follow-tags origin standard-version && npm publish` to publish
```

### License

Apache 2

### Linter

We use eslint and extend semistandard.

### Git hooks

npm >= 7

```
npm install husky -D
npm set-script prepare "husky install" && npm run prepare
npx husky add .husky/pre-commit "npm test"
```

npm < 7

```
npm install husky -D
```

Add to package.json
```
 "scripts": {
    "prepare": "husky install",
```

Run the commands
```
npm run prepare
npx husky add .husky/pre-commit "npm test"
```

### Testing

Testing framework is dependant on the project. The Reference Architecture recommendations are for Mocha or Jest. The nodeshift team has been using Tape in the past.

### Coverage

We have been using the nyc module for code coverage as well as coveralls.io for hosting the results.

### Support

It is recommended to add a support:true property in the package.json and also include the package-support.json.

### Gitignore

A node related .gitignore can be created with `npx gitignore node`.

### Git Actions

#### CI
The nodeshift org is now using Github actions for its CI.  Included in this repo is a copy of what is being used in the other repos.

#### Docs
The nodeshift org now uses Github actions to run and publish docs under the gh_pages branch on github for each release.  Included in this repo is a copy of what is being used in the other repos.

#### Releases
The nodeshift org now uses the Release-please github action to automate the release PRs.  Included in this repo is a copy of what is being used in the other repos.
