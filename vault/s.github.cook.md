---
id: L80sFsAAcOO_0ztqZrN1J
title: Cook
desc: ''
updated: 1625329160942
created: 1625329160942
---

### Use ssh key for github
- source: [Connecting to GitHub with SSH](https://docs.github.com/en/github/authenticating-to-github/connecting-to-github-with-ssh)



#### Generate ssh key
- source: [Generating a new SSH key and adding it to the ssh-agent](https://docs.github.com/en/free-pro-team@latest/github/authenticating-to-github/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent)

```bash
ssh-keygen -t ed25519 -C "your_email@example.com"
```

#### Add ssh key

- source: [Adding a new SSH key to your GitHub account](https://docs.github.com/en/free-pro-team@latest/github/authenticating-to-github/adding-a-new-ssh-key-to-your-github-account)

1. Copy the SSH public key to your clipboard (instructions below for mac)
    ```
    pbcopy < ~/.ssh/id_ed25519.pub
    # Copies the contents of the id_ed25519.pub file to your clipboard
    ```
1. Upload it to github

- NOTE: you can't add a key that's already used elsewhere, see [Error: Key already in use](https://docs.github.com/en/free-pro-team@latest/github/authenticating-to-github/error-key-already-in-use)
