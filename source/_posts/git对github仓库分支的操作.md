---
title:  git对github仓库分支的操作
date: 2021-05-26
tag:  git 
categories: branch
toc: true 
---

#### 分支的查询

```bash
git  branch   ----查询当前分支
git branch -a ----查询所有分支
```

#### 新建分支

```bash
git branch branch-name   ----新建一个名称为branch-name的分支
git checkout --orphan  branch-name  ----新建一个名称为branch-name的无父节点的分支，并自动切换到该分支
```

#### 分支的删除

```bash
在删除分支时，先要确认一下要删除的分支不是当前分支，如果时当前分支的话是不能被删除的，可以使用git checkout branch-name来切换为非当前分支，然后再删除。
git branch -d branch-name   ----删除本地的分支
git push  origin --delete  branch-name ----删除远程仓库分支
```

#### 分支重命名

```bash
git branch -m old-name new-name 
```

#### 分支的切换

```bash
git checkout branch-name 
```

![img](/images/create-empty-branch-to-github.png)

