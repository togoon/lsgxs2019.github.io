---
title: gitshub仓库分支重命名
date: 2021-05-27
tag: 
    -github
    -git
---



#### gitshub仓库分支重命名

在github仓库的分支操作界面改名之后，会提示在本地仓库运行下面的命令

```bash
git branch -m hexo-source source
git fetch origin
git branch -u origin/source source
git remote set-head origin -a
```

