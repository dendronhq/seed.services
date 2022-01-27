---
id: ZPpK7hlt92TPsXgo94j7a
title: Caching
desc: ''
updated: 1643135169951
created: 1632354274744
---

- [Caching dependencies to speed up workflows - GitHub Docs](https://docs.github.com/en/actions/advanced-guides/caching-dependencies-to-speed-up-workflows)


- To cache dependencies for a job, you'll need to use GitHub's `cache` action
- To cache and restore dependencies for npm, Yarn, or pnpm, you can use the `actions/setup-node` action.

- WARNING: don't store any sensitive information in the cache of public repositories

## Limits
- GitHub will remove any cache entries that have not been accessed in over 7 days
- no limit on the number of caches you can store
- total size of all caches in a repository is limited to 5 GB.

## Notes

### Comparing artifacts and dependency caching
- artifacts are for outputs, caching is used for build process

### Restrictions for accessing a cache

- workflow can access and restore a cache created in the **current branch, base branch (including forked repos), and default branch** (eg. `main`)
- **different branches otherwise have cache isolation**
    - /branchA can't access /branchB cache

### Using the cache action
- `cache` action will attempt to restore a cache based on the `key` you provide. 
- action restores the cached files to the `path` you configure
- if no exact match, the **action creates a new cache entry if the job completes successfully**
- optionally provide a list of `restore-keys` to use when the key doesn't match 

- Input parameters for the cache action
    - `path`
        - path can be an absolute path or relative to the working directory.
        - directories or single files, and glob patterns are supported
        ```yml
        - name: Cache Gradle packages
        uses: actions/cache@v2
        with:
          path: |
            ~/.gradle/caches
            ~/.gradle/wrapper
        ```

