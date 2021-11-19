---
id: igJvSY5XEgPRfdqukRKxZ
title: Gh Pages V3
desc: ''
updated: 1634313867765
created: 1631142547164
---
[GitHub - peaceiris/actions-gh-pages: GitHub Actions for GitHub Pages 🚀 Deploy static files and publish your site easily. Static-Site-Generators-friendly.](https://github.com/peaceiris/actions-gh-pages)


```yml
      - name: Deploy site
        uses: peaceiris/actions-gh-pages@v3
        with:
          github_token: ${{ secrets.GITHUB_TOKEN }}
          publish_branch: pages
          publish_dir: docs/
          force_orphan: true
```


## Options

- A source directory to deploy to GitHub Pages. The default is public.

```yml
- name: Deploy
  uses: peaceiris/actions-gh-pages@v3
  with:
    github_token: ${{ secrets.GITHUB_TOKEN }}
    publish_dir: ./out  # default: public
```