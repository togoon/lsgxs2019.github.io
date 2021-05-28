---
title:  git对github仓库分支的操作
date: 2021-05-26
tag:  git 
categories: branch
toc: true 
---

#### 分支的查询

```
git  branch   ----查询当前分支
git branch -a ----查询所有分支
```

#### 新建分支

```
git branch branch-name   ----新建一个名称为branch-name的分支
git checkout --orphan  branch-name  ----新建一个名称为branch-name的无父节点的分支，并自动切换到该分支
```

#### 分支的切换

```
git checkout branch-name 
```

#### 分支的删除

```
git branch -d branch-name   ----删除本地的分支
git remote --delete  branch-name ------待核实，不确定准确写法
```

#### 分支的修改

```
git rename   ----  待核实
```



