# User Story Tips
## User story 编写
### Description
例如：
* 解决什么问题：XXXXXXXX
* 对软件现有功能会造成什么影响：XXXXXX
* 实现的具体的功能：XXXXXX
* 实现时需要考虑的技术细节：XXXXXX

### DoD (Definition of Done)
例如:
- 代码实现符合详细设计和上述描述要求，没有严重 bug
- 代码更改要创建相应的 git pull request ，并由团队成员 review 和 approve ，测试无误后提交到开发主分支
- 代码更改要有相应的测试用例和测试结果 (Unit testing, API testing or manual testing)，证实满足上述 description 的要求


## 优先级 Priority
P1(Must have) / P2(Should have) / P3(Could have) / P4(Won't have)

## 估计工作量

对于比较大的 feature, 我们可以用 t-shirt size 来大致评估

* Small (S) = 1–4 days
* Medium (M) = 5–10 days
* Large (L) = 10–20 days
* Extra Large (XL) = more than 20 days

对于拆分过的 story , 我们可以根据复杂度，风险程度以及重复度用 Story point 来做工作量评估
Story Point 故事点是一种度量单位，用于表达完成特定用户故事、冲刺或产品待办事项列表项所需的总体工作量的估计。
例如可用一个常用实体的增删改查，例如用户的 CRUD 来表示一个故事点

* Complexity: 复杂度，这项工作有多难做?
* Risks: 风险程度，有无第三方依赖和不确定因素？ 
* Repetition: 重复度，是重复性的工作，一次性的工作，还是探索性的工作？


