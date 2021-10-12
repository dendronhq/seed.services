---
id: gIQIoFXSEZpKhGuED5qbK
title: Limits
desc: ''
updated: 1632353841292
created: 1632353779531
---

[Usage limits, billing, and administration - GitHub Docs](https://docs.github.com/en/actions/learn-github-actions/usage-limits-billing-and-administration)

- Each job in a workflow can run for up to 6 hours of 
-  Each workflow run is limited to 72 hours

- API requests - You can execute up to 1000 API requests in an hour across all actions within a repository. If exceeded, additional API calls will fail, which might cause jobs to fail.
- Concurrent jobs - The number of concurrent jobs you can run in your account depends on your GitHub plan, as indicated in the following table. If exceeded, any additional jobs are queued.
    * GitHub plan	Total concurrent jobs	Maximum concurrent macOS jobs
    * Free	20	5
- Job matrix - A job matrix can generate a maximum of 256 jobs per workflow run. This limit also applies to self-hosted runners.
- Workflow run queue - No more than 500 workflow runs can be queued in a 10 second interval per repository. If a workflow run reaches this limit, the workflow run is terminated and fails to complete.







