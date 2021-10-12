---
id: 5H9mqUPYaoWcFkHbi667n
title: Expressions
desc: ''
updated: 1633561251862
created: 1633557844338
---

[Expressions - GitHub Docs](https://docs.github.com/en/actions/learn-github-actions/expressions)


```yml
steps:
  - uses: actions/hello-world-javascript-action@v1.1
    if: ${{ <expression> }}
```

## Functions

- NOTE: need to use `'` instead of `"` for quotes

### endsWith( searchString, searchValue )