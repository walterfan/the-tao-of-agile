# Merge Request Rules

Merge request 也称 Pull request, 在实践过程中，总结了如下的规则

1. 如无特殊需求，所有的开发都是基于 master branch 的, merge request 来自于你的开发分支(feature branch, hot-fix branch, etc) 与 master branch 的比较

2. 所有对于 master branch 的改动都必须通过 merge request 完成

3. 所有的 merge request 必须引用一个对应的 git issue (user story or bug)

  * 3.1 通过 git commit message 来引用相关的 git issue, 格式如下

  ```
  git commit -m "this is my commit message. Ref projectname#xxx" 
  git commit-m "fix memory leak issue. Ref issue#123"
  ```

  * 3.2 在 merge request 的描述里提及相应的 git issue

4. Merge request 必须至少由一位相关领域的同事 Review 并 approve 后， 才可以合并

5. Merge request 不宜过大，一般在200行之内，最多不超过 500行，较大的改动推荐分批审阅

  * 5.1 例如将一个大的 MR 分成三个小的 MR ,  "#123 Refactoring Domain objects 1/3, 2/3, 3/3"
  * 5.2 MR 应包含相应的测试代码，测试代码不计算在上述所说的 MR 行数

6. Merge request 应该有相应的描述信息，让 Reviewer 知道 MR 的目的，动机和范围，比较大的改动需要有附上相关的设计文档

7. Merge Request 要通过 CI pipeline 所定义的单元测试，集成测试，静态代码扫描(没有编译及代码静态分析警告)

  * 7.1 没有通过 CI pipeline 的 MR 不允许合并
  * 7.2 没有 CI pipeline 的项目必须要尽快建立 CI pipeline

8. Merge Request 在合并到主分支时应只包含一个 commit, 如果有多个 commit 请合并成一个(rebase and squash)，在 Commmit message 中包含相关的 git issue, 其目的是为了有效地回溯代码历史， 以便快速定位引入问题的提交

9. Merge Request 牵涉到功能性的改动，要有足够的日志(log)或度量(metrics), 以便在产线上检查及 debug

10. Merge Request 如果有不确定的风险或者用户体验上的变动，要能够用 feature toggle 或 configure item 启用或关闭相应的变动