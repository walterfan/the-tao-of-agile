# git rules

## git repo rules


1. 所有正式的代码仓库请放置于所在的 prject group (或称 organization) 内

   
2. 代码仓库的名字只允许包含小写字母和横线
  例如 frontend/blog-admin

3. 代码仓库的名字应容易理解

   3.1. 可以使用众所所周知的缩写，少用慎用难懂的缩写
  
   3.2. 尽量使用英文单词表达含义，不用拼音

4. 每个代码仓库都必须有一个 README.md 文件，描述这个仓库的基本信息
   包括这个仓库的目的，构建步骤，重大修改历史等等


## git branch rules

每个代码仓库最新的代码必须存放于 master 分支

1. master 分支中的代码可能是不稳定的，应尽量保持 master 分支中的代码是可工作的，推荐使用 feature toggle 来控制新功能的启用和关闭

2. 经充分测试后，开发会基于 master 分支拉出一个 release 分支， 例如 relase/v1.0.0 作为产品发布的候选分支

3. 在 release 分支中的代码是稳定的，如果有紧急问题需要修复，建立 hotfix 分支，通过 merge request 经 approve 后合并至 release 和 master 分支

4. 所有的修改必须创建 pull request(或称 merge request) ，经过团队成员审阅批准后方可合并到 master 或 release 分支 

5. 除了 master 分支，建议的分支名可以是

- 修改bug分支: bugfix/bug-summary, 例如 bugfix/fix-memory-leak

- 紧急修改分支: hotfix/hotfix-summary, 例如 hotfix/fix-crash

- 发布分支: release/version， 例如 release/v1.0.0

- 特性分支: feature/feature-summary, 例如 feature/performance-optimzation

- 个人开发分支: dev/name-summary, 例如 dev/yamin-upgrade-lib