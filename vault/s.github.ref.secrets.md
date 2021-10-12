---
id: xVP34rOY7JhNCh8pNQveX
title: Secrets
desc: ''
updated: 1633452951976
created: 1633452535124
---

[Encrypted secrets - GitHub Docs](https://docs.github.com/en/actions/security-guides/encrypted-secrets)


- Secrets are encrypted environment variables that you create

## Access
-  you must set the secret as an input or environment variable in the workflow file.

- Warning: GitHub automatically redacts secrets printed to the log, but you should avoid printing secrets to the log intentionally.


```yml
steps:
  - shell: bash
    env:
      SUPER_SECRET: ${{ secrets.SuperSecret }}
    run: |
      example-command "$SUPER_SECRET"
```