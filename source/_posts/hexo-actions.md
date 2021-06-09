---
title: hexo actions
date: 2021-05-28
tag: actions
---



* actions-1

```yaml
name: Main workflow

on:
  push:
    branches:
    - raw

jobs:
  build:

    runs-on: ubuntu-18.04

    steps:
    - uses: actions/checkout@v2
    - name: Use Node.js lts
      uses: actions/setup-node@v2-beta
      with:
        node-version: '12.x'
    - name: prepare build env
      env:
        GH_ACTION_DEPLOY_KEY: ${{ secrets.GH_ACTION_DEPLOY_KEY }}
        NEXT_VERSION: v8.0.0-rc.2
      run: |
        mkdir -p ~/.ssh/
        echo "$GH_ACTION_DEPLOY_KEY" > ~/.ssh/id_rsa
        chmod 600 ~/.ssh/id_rsa
        ssh-keyscan github.com >> ~/.ssh/known_hosts
        git config --global user.name 'gythialy'
        git config --global user.email 'gythialy@users.noreply.github.com'
        npm i -g hexo-cli
        npm i
        git clone --branch ${NEXT_VERSION} --depth=10  git@github.com:next-theme/hexo-theme-next.git themes/next
        git checkout -b ${NEXT_VERSION}
        git clone git@github.com:next-theme/theme-next-three --depth=1 themes/next/source/lib/three
        git clone git@github.com:next-theme/theme-next-fancybox3  --depth=1 themes/next/source/lib/fancybox
        git clone git@github.com:next-theme/theme-next-pace --depth=1 themes/next/source/lib/pace
    - name: deploy to github 
      env:
        HEXO_ALGOLIA_INDEXING_KEY: ${{ secrets.HEXO_ALGOLIA_INDEXING_KEY }}
      run: |
        hexo generate && hexo algolia && hexo deploy

```



* atcion-2

  ```yaml
  name: CI
  on:
  push:
  branches:
  - hexo
  jobs:
  build:
  runs-on: ubuntu-latest
  
  steps:
  - name: Checkout source
  uses: actions/checkout@v1
  with:
  ref: hexo
  - name: Use Node.js ${{ matrix.node_version }}
  uses: actions/setup-node@v1
  with:
  version: ${{ matrix.node_version }}
  - name: Setup hexo
  env:
  ACTION_DEPLOY_KEY: ${{ secrets.HEXO_DEPLOY_PRI }}
  run: |
  mkdir -p ~/.ssh/
  echo "$ACTION_DEPLOY_KEY" > ~/.ssh/id_rsa
  chmod 600 ~/.ssh/id_rsa
  ssh-keyscan github.com >> ~/.ssh/known_hosts
  git config --global user.email "lujiahao0708@gmail.com"
  git config --global user.name "lujiahao0708"
  npm install hexo-cli -g
  npm install
  - name: Hexo deploy
  run: |
  hexo clean
  hexo d
  ```

  