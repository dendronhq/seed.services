---
id: DLpmD6IfO5qtIKgh
title: Cache V2
desc: ''
updated: 1632355543998
created: 1627576088900
---

## Summary
- https://github.com/actions/cache

## Input
- restore-keys - An ordered list of keys to use for restoring the cache if no cache hit occurred for key [^1]

## Cook

### generate cache key
```yml
- uses: actions/cache@v2
with:
	path: | 
	path/to/dependencies
	some/other/dependencies 
	key: ${{ runner.os }}-${{ hashFiles('**/lockfiles') }}
```

### Yarn Cache

- source: [^1]
```yml
- name: Get yarn cache directory path
  id: yarn-cache-dir-path
  run: echo "::set-output name=dir::$(yarn cache dir)"

- uses: actions/cache@v2
  id: yarn-cache # use this to check for `cache-hit` (`steps.yarn-cache.outputs.cache-hit != 'true'`)
  with:
    path: ${{ steps.yarn-cache-dir-path.outputs.dir }}
    key: ${{ runner.os }}-yarn-${{ hashFiles('**/yarn.lock') }}
    restore-keys: |
      ${{ runner.os }}-yarn-

```

### Skipping steps based on cache-hit

```yml
steps:
- uses: actions/checkout@v2

- uses: actions/cache@v2
  id: cache
  with:
    path: path/to/dependencies
    key: ${{ runner.os }}-${{ hashFiles('**/lockfiles') }}

- name: Install Dependencies
  if: steps.cache.outputs.cache-hit != 'true'
  run: /install.sh
```


<!-- -->


- [^1]: [GitHub - actions/cache: Cache dependencies and build outputs in GitHub Actions](https://github.com/actions/cache)

## Related
- [[Caching|s.github.t.actions.ref.caching]]
