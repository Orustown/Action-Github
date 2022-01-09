# Action-Github
GitHub的Action自动流程学习，实现自动执行 网易云签到脚本

## 定义

Github Action官方文档中对自身的定义：

> 在 GitHub Actions 的仓库中自动化、自定义和执行软件开发工作流程。 您可以发现、创建和共享操作以执行您喜欢的任何作业（包括 CI/CD），并将操作合并到完全自定义的工作流程中。

用人话说，**就是你可以给你的代码仓库部署一系列自动化脚本，在你进行了提交/合并分支等操作后，自动执行脚本。**

阮一峰Github Action指南中的介绍：

> 大家知道，持续集成由很多操作组成，比如抓取代码、运行测试、登录远程服务器，发布到第三方服务等等。GitHub 把这些操作就称为 actions。
>
> 很多操作在不同项目里面是类似的，完全可以共享。GitHub 注意到了这一点，想出了一个很妙的点子，允许开发者把每个操作写成独立的脚本文件，存放到代码仓库，使得其他开发者可以引用。
>
> 如果你需要某个 action，不必自己写复杂的脚本，直接引用他人写好的 action 即可，整个持续集成过程，就变成了一个 actions 的组合。这就是 GitHub Actions 最特别的地方。

GitHub Actions 有一些自己的术语：

- workflow （工作流程）：持续集成一次运行的过程，就是一个 workflow。
- job （任务）：一个 workflow 由一个或多个 jobs 构成，含义是一次持续集成的运行，可以完成多个任务。
- step（步骤）：每个 job 由多个 step 构成，一步步完成。
- action （动作）：每个 step 可以依次执行一个或多个命令（action）。



## 步骤

在GitHub仓库内添加文件夹`.github/workflow` 或者`.github/workflows`：

> 一个库可以有多个 workflow 文件。GitHub 只要发现.github/workflows目录里面有.yml文件，就会自动运行该文件。

在workflows下编写yml文件，可以有多个yml文件，会自动执行

一个yml脚本便是Action的核心





添加名为 **USER**、**PWD** 的变量，值分别为 **账号（仅支持手机号）**、**密码 **

> Settings-->Secrets-->New secret

支持多账号，账号之间与密码之间用 ***#*** 分隔，账号与密码的个数要对应

示例：**USER:13800000000#13800000001**，**PWD:cxkjntm#jntmcxk**



定时表达式

> on:
>
>   schedule:
>
>    - cron: 0 22,6 * * *

每天以GitHub时区的22点和6点执行，即北京时区的6点和14点



启用Action





[Github Action 快速上手指南](https://www.jianshu.com/p/5406a3a4f3ba)

[白嫖Github Action做定时任务](https://www.jianshu.com/p/2deed352023b)

[京东，百度，网易云音乐自动签到](https://github.com/cc3300/Action-Auto-Sign)

