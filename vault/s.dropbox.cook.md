---
id: NeP6TRXVhbC0o5fxh1o43
title: Cook
desc: ''
updated: 1631378420927
created: 1631378420927
---


## Dropbox - ignore folders
- source: [How to make Dropbox ignore node_modules folder with symbolic links (aliases)](https://www.dropboxforum.com/t5/Dropbox-files-folders/How-to-make-Dropbox-ignore-node-modules-folder-with-symbolic/td-p/388947)

```
cd YOUR_PROJECT_NAME
mkdir -p ~/Downloads/node_modules_for_YOUR_PROJECT_NAME
mv node_modules ~/Downloads/node_modules_for_YOUR_PROJECT_NAME
ln -s ~/Downloads/node_modules_for_YOUR_PROJECT_NAME/node_modules
```