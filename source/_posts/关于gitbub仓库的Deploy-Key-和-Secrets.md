---
title: 关于gitbub仓库的Deploy Key 和 Secrets
date: 2021-05-31
toc: true 
---

## 熟悉Github仓库权限的几个要素

* Token
* SSh
* Deploy key
  * Deploy key 实际是一个限定在指定github仓库的的SSH,而不是作用域为整个github账户。

 A deploy key is an SSH key that is stored on your server and grants access to a single GitHub repository. This key is attached directly to the repository instead of to a personal user account.


* Secrets
  * 这个也可以看做是用在github actios 里的token。一般是先生成一个token ,保存起来，然后把这token 添加在指定仓库的secrets里，在action里可以通过变量的形式引用。

*Note that these tokens have [specific permissions](https://docs.github.com/en/actions/reference/authentication-in-a-workflow#permissions-for-the-github_token), and that depending on what you want to do, you may need to create a [Personal Access Token](https://github.com/settings/tokens) (PAT) and add it as a secret (ex: ACCESS_TOKEN) to use in your workflow.*

* [Authentication in a workflow - GitHub Docs](https://docs.github.com/en/actions/reference/authentication-in-a-workflow)

