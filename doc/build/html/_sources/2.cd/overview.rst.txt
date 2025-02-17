######################
持续交付概述
######################

.. include:: ../links.ref
.. include:: ../tags.ref
.. include:: ../abbrs.ref

============ ==========================
**Abstract** 持续交付概述
**Authors**  Walter Fan
**Status**   WIP as draft
**Updated**  |date|
============ ==========================

.. contents::
   :local:


Overview
=======================

What's CI
-----------------------  

Continuous integration automates the builds, provides feedback via code review, and automates code quality and security tests. It creates a release package that is ready to be deployed to your production environment.

What's CD
-----------------------
Continuous delivery automatically provisions infrastructure, manages infrastructure changes, ticketing, and release versioning. It allows, progressive code deployment, verifying and monitoring changes made and providing the ability to roll back when necessary. Together, GitLab Continuous Integration and Delivery help you automate your SDLC, making it repeatable and on-demand with minimal manual intervention


Build Pipeline
=======================

1. CI 环境
   
  1. build server(jenkins agent or gitlab runner)
  2. TA environment 用来做 merge request 的验证
   
2. CI 工具
   
  - merge request 可触发 build pipeline（包括代码静态检查，单元测试， api test, document generation, etc.）
  - 只有 build pipeline 通过， merge request approve, 代码才可合并到主分支(master branch)
  
  1. 使用 Jenkins 和 Gitlab runner 来驱动整个 build pipeline
  2. 使用 ansible 来进行系统依赖的安装配置，并部署软件包

3. CI 步骤

.. image:: ../_static/buid-pipeline.drawio.png
  :width: 800
  :alt: build pipeline

1. CI 自动化流水线的构建: Jenkins and Gitlab runner 
2. 代码规范检查和静态代码扫描
3. 单元测试
4. API 测试
5. 自动生成文档
6. 自动上传制成品