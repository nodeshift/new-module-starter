# New Module Starter

This repo is for reference when creating a new node module/application in the nodeshift org.


## Minimum requirements

### Commit Messages

We have been trying to adhere to coventional commits, https://www.conventionalcommits.org/en/v1.0.0/ , which helps when creating our changelogs and releases.

We also try to stay away from merge commits to keep the git history clean.

### License

Apache 2

### Linter

We use eslint and extend semistandard.

### Testing

testing framework is dependant on the project.  The Reference Architecture recommendations are for Mocha or Jest.  The nodeshift team has been using Tape in the past

### Coverage

We have been using the nyc module for code coverage as well as coveralls.io for hosting the results


### Support

It is recommended to add a support:true property in the package.json and also include the pacakge-support.json

### Gitignore

A node related .gitignore can be created with `npx gitignore node`

### Git Actions

#### CI
The nodeshift org is now using Github actions for its CI.  Included in this repo is a copy of what is being used in the other repos

#### Docs
The nodeshift org now uses Github actions to run and publish docs under the gh_pages branch on github for each release.  Included in this repo is a copy of what is being used in the other repos

#### Releases
The nodeshift org now uses the Release-please github action to automate the release PRs.  Included in this repo is a copy of what is being used in the other repos
