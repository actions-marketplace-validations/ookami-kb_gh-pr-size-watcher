# PR Size Watcher

Checks PR for a total number of additions. To use the action put this into your Workflows file:

```yaml
name: PR Size Watcher
on: [pull_request]

jobs:
  build:
    name: Check PR size
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v1
      - uses: ookami-kb/gh-pr-size-watcher@v1
        with:
          GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}
```

You can specify additional options:

```yaml
with:
    errorSize: 500
    errorMessage: ':no_entry: PR has more than **{allowed} additions**. Split it into smaller PRs.'
    warningSize: 300
    warningMessage: ':warning: PR has more than **{allowed} additions**. Consider splitting it into smaller PRs.'
    excludeTitle: 'PR_SIZE_SKIP' # to skip validation if PR title matches regex
```
