# Draw.io Examples Template

Use these as starter patterns when the deliverable should be a maintainable `.drawio` source file plus exported PNG/SVG/PDF artifacts.
Do not cargo-cult the exact nodes — replace them with the target system’s actors, services, stages, branch conditions, and terminal states.

## 1. 角色/阶段驱动的主流程图（Flowchart）

建议元素清单：
- Actor / Trigger：圆角矩形，左侧起点
- Gateway / Intake：圆角矩形
- Decision：菱形
- Core Service：圆角矩形
- Controlled Failure：红色圆角矩形
- Notification / External：中性圆角矩形
- Store：圆柱体
- Manual Ownership：蓝色圆角矩形

建议连线：
- `submit` → Actor / Trigger → Gateway / Intake
- `validate` → Gateway / Intake → Decision
- `pass` → Decision → Core Service
- `reject` → Decision → Controlled Failure
- `emit result` → Core Service → Notification / External
- `persist` → Core Service → Store
- `timeout` / `manual takeover` → Core Service → Manual Ownership → Notification / External

适用：
- 审批 / 路由 / 编排 / 核心闭环
- 角色与阶段切换明显
- 分支条件需要明确表达

## 2. 事件驱动链路图（Event Mesh / Async Flow）

建议元素清单：
- Producer Service：圆角矩形
- Event Bus：横向总线 / 队列形态，居中
- Processor Service：圆角矩形
- Store：圆柱体
- Notifier Service：圆角矩形
- External / Actor：中性外部节点
- Retry / Pending Owner：蓝色补偿/待处理节点

建议连线：
- `publish:event.created` → Producer Service → Event Bus
- `consume` → Event Bus → Processor Service
- `write` → Processor Service → Store
- `publish:event.processed` → Processor Service → Event Bus
- `consume` → Event Bus → Notifier Service
- `notify` → Notifier Service → External / Actor
- `timeout` → Processor Service → Retry / Pending Owner

适用：
- 最终一致性
- 发布/消费模型
- 事件总线主导的处理链

## 3. Saga / 补偿流模板

建议元素清单：
- Step 1..4：统一样式的执行步骤节点
- Undo Step 2 / Undo Step 3：红色补偿步骤节点
- Success：绿色终态
- Rollback Complete：红色终态

建议连线：
- 主路径：Step 1 → Step 2 → Step 3 → Step 4
- 成功路径：Step 3 / Step 4 → Success
- 失败路径：Step 3 `failure` → Undo Step 3 → Undo Step 2 → Rollback Complete

适用：
- 长事务
- 可补偿业务流
- rollback 是评审重点

## 4. 状态机模板（State Lifecycle）

建议元素清单：
- Pending
- Processing
- PendingReview
- Failed
- Success
- Cancelled
- Start / End 可用小圆或文字起止点

建议状态迁移：
- accepted: Pending → Processing
- cancel: Pending → Cancelled
- complete: Processing → Success
- fail: Processing → Failed
- timeout / manual takeover: Processing → PendingReview
- resume: PendingReview → Processing
- abort: PendingReview → Cancelled
- retry-allowed: Failed → Pending
- retry-forbidden: Failed → Cancelled

适用：
- 状态闭环比步骤编排更重要
- retry / cancel / pending ownership 很关键

## Draw.io 使用注意事项

- 优先把语义差异体现在**形状、颜色、边界和线型**上，而不是只靠节点名解释。
- 容器/边界优先用 `Container` / `Swimlane` 表达，不要把逻辑分组画成普通背景块。
- 若一个图同时需要表达主路径与异常/补偿路径，优先通过颜色 + 虚线/实线区分，而不是把所有说明堆到注释文字里。
- 每次交付默认保留 `.drawio` 源文件，并导出至少一个面向阅读者的 PNG 或 SVG。
- 如果 Draw.io 仍然难以清楚表达讨论态草图，就不要硬撑；转 Excalidraw。