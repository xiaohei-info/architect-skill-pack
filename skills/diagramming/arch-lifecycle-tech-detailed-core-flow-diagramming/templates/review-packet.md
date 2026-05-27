# Core Functional Flow Review Packet Template

Use this packet when handing a diagram to reviewers. Fill it out beside the figure so the review stays anchored on the right questions.

## 1. Scope Statement
- 本图回答的关键流程是：
- 该流程所在阶段：
- 本图的目标读者：

## 2. Artifact Type
- 图类型：Flowchart / State Machine / Flow + State Supplement
- 为什么选这个图类型而不是相邻图种：

## 3. Trigger / Owner / Outcome
- Trigger source：
- Primary business object（如有）：
- First owner：
- Final success state：
- Final failure / cancel / pending states：

## 4. Main Path Summary
- 主路径一句话：
- 主路径步骤（3-7 步）：
  1.
  2.
  3.
  4.
  5.

## 5. Branch Inventory

### Branch A
- 条件 / trigger：
- 分支类型：normal / exception / rollback / retry / cancel / pending / degrade
- 处理逻辑：
- 终结态 / 下一个决策点：

### Branch B
- 条件 / trigger：
- 分支类型：
- 处理逻辑：
- 终结态 / 下一个决策点：

### Branch C
- 条件 / trigger：
- 分支类型：
- 处理逻辑：
- 终结态 / 下一个决策点：

## 6. Role / Stage Handoffs
- 关键角色：
- 关键阶段：
- ownership change points：

## 7. Review Risks
- 最容易遗漏的分支：
- 最容易被误画成技术架构的位置：
- 最容易被误画成接口/数据明细的位置：
- 如果 reviewer 提出“这不是流程图”的风险点：

## 8. Companion Artifacts
- 是否有状态机补充：
- 是否有异常流补充：
- 是否有外部系统补充图：

## 9. Out-of-Scope Notes
- 本图明确不覆盖：
- 对应应转去的 artifact：

## 10. Reviewer Checklist
- [ ] 主路径清楚
- [ ] 分支条件清楚
- [ ] 终结态清楚
- [ ] ownership 清楚
- [ ] 不重不漏
- [ ] 没有漂移成别的图种
