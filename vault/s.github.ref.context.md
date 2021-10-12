---
id: wz9ixYe1t788ta6sQd6jU
title: Context
desc: ''
updated: 1633557757353
created: 1632353526973
---

https://docs.github.com/en/actions/learn-github-actions/contexts#github-context


## objects

### github
- Warning: When using the whole github context, be mindful that it includes sensitive information such as github.token

#### github.ref
- The branch or tag ref that triggered the workflow run. For branches this is the format refs/heads/<branch_name>, and for tags it is refs/tags/<tag_name>.

```yml
name: CI
on: push
jobs:
  prod-check:
    if: ${{ github.ref == 'refs/heads/main' }}
    runs-on: ubuntu-latest
    steps:
      - run: echo "Deploying to production server on branch $GITHUB_REF"

```

## Functions

### contains

### toJSON

### hashFiles

hashFiles('**/package-lock.json')


## Job Status Check

### success

```yml
steps:
  ...
  - name: The job has succeeded
    if: ${{ success() }}
```