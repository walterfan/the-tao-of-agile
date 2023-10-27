# gitlab CI

## gitlab runner

1. 确保您有可用的 runner 运行您的作业。 如果您没有 runner，需要为您的示例、项目或群组安装 GitLab Runner并注册 runner。
2. 在仓库的根目录下创建一个 .gitlab-ci.yml 文件。该文件是您定义 CI/CD 作业的地方。

## gitlab build pipeline

流水线是持续集成、交付和部署的顶级组件。

流水线包括：

* job 工作，定义做什么。例如，编译或测试代码的作业。
* stage 阶段，定义何时运行作业。例如，在编译代码的阶段之后运行测试的阶段。

job 由 runners 执行。如果有足够多的并发运行程序，同一阶段的多个 job 将并行执行。

如果一个阶段中的所有 job 成功，流水线将进入下一个阶段。

如果某个 stage 中的任何job 失败，则下一个job （通常）不会执行并且流水线提前结束。

一般来说，流水线是自动执行的，一旦创建就不需要干预。但是，有时您也可以手动与流水线交互。

一个典型的流水线可能包含四个阶段，按以下顺序执行：

1. 一个 build 阶段，有一个名为 compile 的 job。
2. 一个 test 阶段，有两个名为 unit-test 和 integration-test 的 job。
3. 一个 staging 阶段，有一个名为 deploy-to-stage 的 job。
4. 一个 production 阶段，有一个名为 deploy-to-prod的 job。


## 参考资料
* https://docs.gitlab.com/ee/ci/pipelines/
* https://docs.gitlab.cn/jh/ci/pipelines/