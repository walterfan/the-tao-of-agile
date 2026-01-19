
# 敏捷方法

> 图难于其易，为大于其细；
> 
> 天下难事，必作于易； 
> 
> 天下大事，必作于细。
> 
> 是以圣人终不为大，故能成其大
> 
> 老子

> 不积跬步，无以至千里；
> 
> 不积小流，无以成江海。
> 
> 骐骥一跃，不能十步；
> 
> 驽马十驾，功在不舍
> 
> 荀子


敏捷是一种方法, 代表一种精神, 让事情变得简单高效, 就象 XP 创始人 Kent Back 所说的快速地拥抱变化.

所以敏捷的精神在于快速的应对变化, 告别冗长的流程, 专注于提供对于用户有价值的软件.


## 敏捷宣言

我们一直在实践中探寻更好的软件开发方法， 身体力行的同时也帮助他人。由此我们建立了如下价值观：

    个体和互动 高于 流程和工具 
    工作的软件 高于 详尽的文档 
    客户合作 高于 合同谈判 
    响应变化 高于 遵循计划

也就是说，尽管右项有其价值， 我们更重视左项的价值

## 敏捷原则

1. 通过快速交付有用的软件来满足客户需求
1. 欢迎不断变化的需求，即使是在开发后期
1. 工作软件频繁交付（几周而不是几个月）
1. 业务人员和开发人员之间密切的日常合作
1. 项目是围绕有积极性的个人建立的，这些人应该值得信任
1. 面对面交谈是最好的沟通方式（同地办公）
1. 可以工作的软件是衡量进度的主要标准
1. 可持续发展，能够保持恒定的步伐
1. 持续关注卓越技术和良好设计
1. 简单性 — 最大化未完成工作量的艺术非常重要
1. 自组织团队
1. 定期适应不断变化的情况


## 精益思想

确保团队采用的流程要有助于构建对客户有价值的产品 

    MMF 最小市场特性
    MVP 最小可行产品

1. 消除浪费
1. 增强学习
1. 推迟决定
1. 尽快交付
1. 授权团队

## Scrum

以相对固定的几周一个迭代周期(Sprint), 以跨职能,自组织的 Scrum team 持续交付对用户有价值的软件. 它比较强调节奏感, 仪式感, 可操作性强, 在多数互联网公司中广泛应用
Scrum 是一个轻量的框架，它通过提供针对复杂问题的自适应解决方案来帮助人们、团队和组织 创造价值。
简而言之，Scrum 需要 Scrum Master 营造一个环境，从而：

* 一名 Product Owner 将解决复杂问题所需的工作整理成一份 Product Backlog。
* Scrum Team 在 一个 Sprint 期间将选择的工作 Sprint Backlog 转化为有价值的 Increment。
* Scrum Team 和利益攸关者检查结果并为下一个 Sprint 进行调整。
* 重复以上步骤

### Scrum 的价值观

1. 承诺：致力于达成其目标并且相互支持。
1. 专注：主要关注点是 Sprint 的工作，以便尽可能地向着这些目标获取最好的进展。
1. 开放：对工作和挑战持开放态度。
1. 尊重：相互尊重，彼此是有能力和独立的人，并因此受到与他们一起工作的人的尊重。
1. 勇气：有勇气做正确的事并处理那些棘手的问题


### Scrum 的 3-5-3 要点

* 3 种角色：

  1. 产品负责人（Product Owner）
  2. Scrum Master
  3. Scrum团队

* 5 种事件:

  1. Sprint 冲刺过程
  2. Sprint计划会议（Sprint Planning Meeting）
  3. 每日站会（Daily Scrum Meeting）
  4. Sprint评审会议（Sprint Review Meeting）
  5. Sprint回顾会议（Sprint Retrospective Meeting）

* 3 种工件:

  1. 产品Backlog（Product Backlog）
  1. SprintBacklog（Sprint backlog）
  1. Increment（产品增量）


# 敏捷实践
## 1. User Story Writing Guide

### 1.1 采用 Role-Action-Benefit 格式 例如
- "As a Role, I want to Action, so that benefit"
- 作为一个招聘者，我想在各大招聘平台发布新的职位信息，从而让应聘者方便快捷地发现我们的职位并来求职

### 1.2 User Story 讲究 INVEST 原则
- "I" ndependent (of all others) 独立的: 每个用户故事应该代表一组独特且独立的业务价值，这样，如果它单独发布，它将比之前的状态提供增量价值。
- "N" egotiable (not a specific contract for features) 可协商的: 虽然最终目标可能被清楚地描述，但实现该目标的方法应该是可协商的——在产品负责人和开发团队、产品负责人和客户或任何其他相关利益相关者之间——以防止对特性或功能的不切实际的要求
- "V" aluable (or vertical) 有价值的： 任何用户故事的商业价值都应该通过阅读故事而容易被识别，并且每个故事都应该代表特定用户类型的某种价值
- "E" stimable (to a good approximation) 可估量的： 我们必须有足够的信息来正确确定故事的大小，以便我们可以正确地计划和致力于我们的工作
- "S" mall (so as to fit within an iteration) 足够小的， 用户故事应该足够小，以便能够在一个 sprint 冲刺内完成
- "T" estable (in principle, even if there isn't a test for it yet) 可测试的: 团队的所有成员都需要一种清晰、准确的方法来验证用户故事是否已完成

### 1.3 User Story 要清楚地描述此用户故事可被接受为完成的条件 DoD (Definition of Done)
如有设计文档，请提供文档链接, 并通过了相关团队成员的审阅(review and signoff)

如有代码更改：

- 代码更改要创建相应的 git pull request ，并由团队成员 review 和 approve ，测试无误后合并到主开发分支
- 代码更改要有相应的测试用例和测试结果 (Unit testing, API testing or manual testing)
- 代码实现符合详细设计和上述描述要求，没有严重 bug，通过 Acceptance Test Case

### User Story Priority

Priority 优先级 (MoSCoW Prioritization Method)

* P1 – Must have: What is described in the User Story must be developed compulsorily.
  必须有, 紧急并重要的任务  Urgent + Important
* P2 – Should have: The User Story should be developed if possible.
  应该有，不紧急但重要的任务 Important
* P3 – Could have: It could be developed, but it is not essential for users or business teams.
  可以有, 紧急但不重要的任务  Urgent
* P4 – Won't have: It won't be included in the medium term, but it could be useful in a later version.
  最好有, 也可以没有，不紧急也不重要的任务

### Example

作为一名 RFC 的读者，我想快速将英文写的协议文本翻译成中文，并更新索引，这样我就能以母语快速掌握协议要点

#### Description
- 英文的 RFC 的输入可以是 txt 或者 pdf 格式，中文的 RFC 的输出可以是相同的格式
- 文本的翻译可以调用 Google, Bing 或者 Baidu 的 API, 要求是免费并且快速, 对文本的长度没有过多限制（可翻译至少 100页文本）

#### DoD (Definition of Done)
- 代码实现符合详细设计和上述描述要求，没有严重 bug
- 代码更改要创建相应的 git pull request ，并由团队成员 review 和 approve ，测试无误后提交到开发主分支
- 代码更改要有相应的测试用例和测试结果 (Unit testing, API testing or manual testing)，证实满足上述 description 的要求

## Bug Report Guide
### 报 Bug 所需要的内容 

1) Defect ID
2) Defect Title
3) Defect Description: 实际的结果以及期望的结果
4) Steps to Reproduce
5) Environment
6) Severity and Priority
7) Evidence
8) Other Comments

### Bug Severity

S1. Block issue
S2. Critical issue
S3. Major issue
S4. Minor issue
S5. Trival issue


In **Agile / Scrum**, **DoR** and **DoD** are two lightweight but *very powerful* agreements that keep teams from drifting into chaos or endless rework.

---

## 1️⃣ DoR — *Definition of Ready*

**Question it answers:**
👉 *“Is this work item ready to be pulled into a sprint?”*

### What DoR means

A **Definition of Ready** is a checklist that a **User Story / backlog item must satisfy before the team starts working on it**.

If a story is **not “Ready”**, it should **not enter the sprint**.

### Typical DoR criteria

A story is “Ready” when:

* ✅ Clear **business value**
* ✅ Well-written **user story**
* ✅ **Acceptance criteria** defined
* ✅ Dependencies identified (or resolved)
* ✅ Testable
* ✅ Estimated (or small enough to estimate)
* ✅ No obvious ambiguity

### Example DoR

```text
A user story is Ready when:
- Business goal is understood
- Acceptance criteria are written
- Dependencies are identified
- Team agrees it can be completed in one sprint
```

### Why DoR matters

* Prevents “We don’t know what to do” mid-sprint
* Reduces interruptions & re-planning
* Protects the sprint commitment

> 💡 Without DoR, sprint planning becomes gambling.

---

## 2️⃣ DoD — *Definition of Done*

**Question it answers:**
👉 *“Can we truly say this work is finished?”*

### What DoD means

A **Definition of Done** is a shared agreement on **what “done” really means**.

Not “code finished”, but **production-ready**.

### Typical DoD criteria

A story is “Done” when:

* ✅ Code completed
* ✅ Code reviewed
* ✅ Unit tests written & passing
* ✅ Integration tests passed
* ✅ Meets acceptance criteria
* ✅ Documentation updated
* ✅ No critical bugs
* ✅ Deployable / deployed

### Example DoD

```text
A story is Done when:
- Code merged to main branch
- All CI checks pass
- Acceptance criteria satisfied
- No critical defects
- Ready for release
```

### Why DoD matters

* Avoids “90% done” forever
* Ensures consistent quality
* Makes velocity meaningful
* Builds trust with stakeholders

> 💡 Without DoD, “done” becomes a negotiation every sprint.

---

## 3️⃣ DoR vs DoD (Side-by-Side)

| Aspect   | DoR                 | DoD                    |
| -------- | ------------------- | ---------------------- |
| Timing   | Before sprint       | End of work            |
| Focus    | Clarity & readiness | Quality & completeness |
| Protects | Sprint planning     | Product quality        |
| Question | “Can we start?”     | “Can we release?”      |

---

## 4️⃣ Common Anti-Patterns 🚨

### ❌ Treating DoR as a gatekeeping bureaucracy

* DoR is a **team agreement**, not a weapon

### ❌ DoD is different for every story

* DoD must be **consistent across the team**

### ❌ “Code complete” = Done

* That’s *Waterfall thinking in Agile clothing*

---

## 5️⃣ A Simple Mental Model

Think of Agile work like cooking:

* **DoR** → *Ingredients prepared & recipe understood*
* **DoD** → *Dish cooked, plated, and safe to serve*

---

## 6️⃣ Pro Tip (from experienced teams)

* Start **simple**
* Evolve DoR & DoD **retrospectively**
* Write them down **where everyone can see**

