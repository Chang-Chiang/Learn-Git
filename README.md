# Learn-Git
Git、GitHub、GitLab 相关使用操作记录

## 目录

- [背景](#背景)
- [环境准备](#环境准备)
- [Git基础](#Git基础)
- [项目修改记录](#项目修改记录)
    - [新建 Git 环境，管理项目](#新建 Git 环境，管理项目)
    - [查看当前项目状态]()
    - [查看修改文件前后差异]()
    - [项目修改文件加入追踪]()
    - [撤回追踪]()
    - [提交追踪文件]()
    - [查看提交日志]()
    - []()
    - []()
    - []()
- []()
- []()
- []()

## 背景

- 记录项目代码变化过程：开发者、时间、提交内容
- 备份每一个变化过程的代码版本：历史记录、复原变更、比较差异
- 多人协同开发：分支合并、克隆提交

## 环境准备

> Git 官网：https://git-scm.com，下载安装即可

- 查看版本：`git --version`

- 帮助文档：`git help`

- 配置用户名和邮箱

    ```shell
    git config --global user.name "Chang Chiang"
    git config --global user.email Chang_Chiang@outlook.com
    
    # 查看配置
    git config --list
    
    # 查看配置用户名
    git config user.name
    ```

## Git 基础

- 工作区
- 暂存区
- 仓库

## 项目修改记录

### 新建 Git 环境，管理项目

```shell
# 查看当前目录
pwd
/Users/cc/tmp

# 初始化 Git 环境，后面 Git 即可对项目进行管理
git init
# 此时 tmp 目录下会多一个 .git 文件夹
# cd /Users/cc/tmp + git init == cd /Users/cc/ + git init tmp
```

### 查看当前项目状态

```shell
git status
```

### 查看修改文件前后差异

```shell
git diff test

git diff --stage
```

### 项目修改文件加入追踪

```shell
git add test  # 修改的 test 文件加进追踪
git add .     # 所有修改文件加进追踪
```

### 撤回追踪

```shell
git rm --cached test  # git add 添加进追踪的文件再放弃追踪
```

### 提交追踪文件

```shell
git commit  # 直接提交

git commit -m "提交说明"  # 附带提交说明提交

git commit -am ""
```

### 查看提交日志

```shell
git log

git log -p -2
git log --author "Chang Chiang"  # 查看哪个 author 的 commit 记录
git log --graph
```

### 文件操作

```shell
git rm test  # 删除 test 文件
git mv test test_new  # test 文件重命名为 test_new
git mv test path_new/test  # test 文件移动至 path_new 路径下
```

### .gitignore 自动不追踪指定文件

```yaml
/filefolder  # 不追踪 指定文件夹下所有文件
*.log        # 不追踪 .log 结尾的所有文件
```

## 项目版本回退

### 查看日志

```shell
git log
```

### 恢复到指定某一次提交状态

```shell
git checkout c9dee4766f75daf16f91f48c4bff08535e4afd01  # checkout 后接 commit id

git reset --hard HEAD  # 回退到上一个版本 
git reset --hard HEAD
git reset --hard HEAD [commit id]  # 回退到指定 commit 版本
```

## 项目分支操作

### 建立、切换、删除分支

```shell
git branch [分支名]  # 创建分支
git checkout [分支名]  # 切换分支
git checkout -b [分支名]
git branch [分支名] -d
git branch [分支名] -D
```

### 合并分支

```shell
git merge [分支名]
```

### 解决合并分支时的冲突

```shell
git merge
git status
git merge -abort
git commit
```

### 查看版本图

```shell
git log
git log -oneline
git log -oneline -graph
git log -oneline -graph -all
git log -oneline -graph -[n]
```

### 删除分支

```shell
git branch --merged | egrep -v "(^*master|develop)" | xargs git branch -d
```

## Git + GitHub

### 注册账号

### 仓库信息

### 远端仓库

- 向远端仓库推文件

    ```shell
    git push
    ```

    

- 从远端仓库拉文件

    ```shell
    git pull
    
    git fetch
    ```

- 合并分支

    ```shell
    git merge
    ```

## Git + GitLab

### 常规 Git 操作

```shell
git init
git status
git add
git commit -m
git push origin -master
```

### 项目间 fork 操作

### CI/CD

- 注册安装 GitLab Runner
- 创建 .gitlab-ci.yml
- 运行 CI/CD Pipelines
