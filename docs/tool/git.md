---
tags:
 - tool
---

# Git命令

## 安装
macOS
  ```bash
  brew install git
  ```

windows
  从 [Git官网](https://git-scm.com/downloads) 下载安装包安装

## 配置
  ```bash
  # 配置用户名和邮箱
  git config-- global user.name "xxxx"                 # 配置全局用户名
  git config --global user.email "xxxx@xxxx.com"      # 配置全局邮箱

  # 配置命令行颜色
  git config --global color.ui true                         # git status等命令自动着色
  git config --global color.status auto                     # git status命令着色
  git config --global color.diff auto                       # git diff命令着色  
  git config --global color.branch auto                     # git branch命令着色
  git config --global color.interactive auto                # git add -i等交互命令着色

  # 取消代理配置
  git config --global --unset http.proxy                    # 取消全局HTTP代理配置
  ```

## 常用命令

### 初始化仓库
  ```bash
  git init
  ```

### 添加文件到暂存区
  ```bash
  git add <file>
  ```

### 提交文件到本地仓库
  ```bash
  git commit -m "提交信息"
  ```

### 查看提交历史
  ```bash
  git log
  ```

### 查看文件状态
  ```bash
  git status
  ```

### 查看文件差异
  ```bash
  git diff
  ```

### 查看分支
  ```bash
  git branch
  ```


### 创建分支
  ```bash
  git branch <branch-name>
  ```

### 切换分支
  ```bash
  git checkout <branch-name>
  ```

### 合并分支
  ```bash
  git merge <branch-name>
  ```

### 删除分支
  ```bash
  git branch -d <branch-name>
  ```

### 查看远程分支
  ```bash
  git fetch <remote-name>
  ```

### 拉取远程分支
  ```bash
  git pull
  ```

### 推送到远程分支
  ```bash
  git push
  ```

### 查看远程仓库
  ```bash
  git remote -v
  ```

### 克隆远程仓库
  ```bash
  git clone <repository-url>
  ```

### 添加远程仓库
  ```bash
  git remote add <remote-name> <repository-url>
  ```

### 删除远程仓库
  ```bash
  git remote rm <remote-name>
  ```

### 新建项目并推送到远程仓库
  ```bash
  # 1. 初始化本地仓库
  git init
  
  # 2. 添加文件到暂存区
  git add .
  
  # 3. 提交到本地仓库
  git commit -m "初始化项目"
  
  # 4. 添加远程仓库
  git remote add origin <repository-url>
  
  # 5. 推送到远程仓库
  git push -u origin master
  ```

### 还原commit
  ```bash
  # 1. 查看提交历史
  git log

  # 2. 还原指定commit
  git revert <commit-id>

  # 3. 提交还原操作
  git commit -m "revert: 还原xxx提交"

  # 4. 推送到远程
  git push origin master
  ```

  ::: tip 说明
  - revert 会创建一个新的提交来撤销指定commit的修改
  - 相比reset更安全,不会丢失提交历史 
  - 适合已经推送到远程的提交回滚
  :::

### 撤销commit
  ```bash
  # 1. 查看提交历史
  git log

  # 2. 撤销最近一次提交(保留修改)
  git reset --soft HEAD^

  # 3. 撤销最近一次提交(丢弃修改)
  git reset --hard HEAD^

  # 4. 撤销指定commit(保留修改)
  git reset --soft <commit-id>

  # 5. 撤销指定commit(丢弃修改)
  git reset --hard <commit-id>
  ```

  ::: tip 说明
  - soft: 撤销commit但保留修改内容在暂存区
  - hard: 撤销commit且丢弃修改内容
  - HEAD^: 表示上一次提交
  - 适合本地提交的撤销,不要用于已推送的提交
  :::

### 多人协作开发新功能
  ```bash
  # 1. 从主分支创建功能分支
  git checkout -b feature/xxx
  
  # 2. 开发完成后提交代码
  git add .
  git commit -m "feat: 完成xxx功能"
  
  # 3. 切回主分支并更新
  git checkout master
  git pull origin master
  
  # 4. 合并功能分支
  git merge feature/xxx
  
  # 5. 解决冲突(如果有)后提交
  git add .
  git commit -m "merge: 合并xxx功能"
  
  # 6. 推送到远程
  git push origin master
  ```

### 代码回滚
  ```bash
  # 1. 查看提交历史
  git log
  
  # 2. 回滚到指定版本
  git reset --hard <commit-id>
  
  # 3. 强制推送到远程(慎用)
  git push -f origin master
  ```

### 紧急修复线上bug
  ```bash
  # 1. 从主分支创建修复分支
  git checkout -b hotfix/xxx
  
  # 2. 修复bug并提交
  git add .
  git commit -m "fix: 修复xxx问题"

  # 3. 合并到主分支
  git checkout master
  git merge hotfix/xxx

  # 4. 推送到远程
  git push origin master

  # 5. 删除修复分支
  git branch -d hotfix/xxx
  ```

### 暂存当前工作
  ```bash
  # 1. 暂存当前修改
  git stash save "暂存xxx功能开发"

  # 2. 切换分支处理其他事情
  git checkout other-branch

  # 3. 回到原分支
  git checkout feature/xxx

  # 4. 恢复暂存的修改
  git stash pop

  # 5. 查看所有暂存记录
  git stash list

  # 6. 查看指定暂存的改动内容
  git stash show stash@{0}  # stash@{0}表示最近一次的暂存记录,{0}是暂存记录的索引,从0开始计数

  # 7. 恢复指定的暂存记录
  git stash apply stash@{0}

  # 8. 删除指定的暂存记录
  git stash drop stash@{0}

  # 9. 清空所有暂存记录
  git stash clear
  ```

  ::: tip 说明
  - 暂存区是用于临时保存修改的区域
  - 适合需要切换分支处理其他事情时,保留当前修改
  - 使用场景: 
  - 适合需要切换分支处理其他事情时,保留当前修改
  :::



