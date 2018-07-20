---
title: VSCode：在签出前，请清理存储库工作树。
date: 2018-07-20 10:31:42
tags: 
  - 问题
  - VSCode
---

关于VSCode在签出更新代码时报错：**在签出前，请清理存储库工作树**，问题主要是git仓库上的代码和本地代码存在冲突。

<!-- more -->

![Alt text](https://s1.ax1x.com/2018/07/20/P3hXUe.png)

> 查看git日志：Please commit your changes or stash them before you merge. Aborting

#### 1.手动解决代码冲突

  {% codeblock 1.切换到git代码目录 %}
    git stash
    git pull
    git stash pop
  {% endcodeblock %}

    2.手动解决冲突文件

git stash: 备份当前的工作区的内容，从最近的一次提交中读取相关内容，让工作区保证和上次提交的内容一致。同时，将当前的工作区内容保存到Git栈中。
git stash pop: 从Git栈中读取最近一次保存的内容，恢复工作区的相关内容。由于可能存在多个Stash的内容，所以用栈来管理，pop会从最近的一个stash中读取内容并恢复。

#### 2.放弃本地修改，直接覆盖

  {% codeblock 切换到git代码目录 %}
    git reset --hard
    git pull
  {% endcodeblock %}