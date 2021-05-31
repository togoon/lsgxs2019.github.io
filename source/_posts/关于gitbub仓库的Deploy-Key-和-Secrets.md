---
title: 关于gitbub仓库的Deploy Key 和 Secrets
date: 2021-05-31
toc: true 
---

## 熟悉Github仓库权限的几个要素

* SSh

* Token 

* Deploy key

  *  A deploy key is an SSH key that is stored on your server and grants access to a single GitHub repository. This key is attached directly to the repository instead of to a personal user account.


* Secrets

*Note that these tokens have [specific permissions](https://docs.github.com/en/actions/reference/authentication-in-a-workflow#permissions-for-the-github_token), and that depending on what you want to do, you may need to create a [Personal Access Token](https://github.com/settings/tokens) (PAT) and add it as a secret (ex: ACCESS_TOKEN) to use in your workflow.*

* [Authentication in a workflow - GitHub Docs](https://docs.github.com/en/actions/reference/authentication-in-a-workflow)

