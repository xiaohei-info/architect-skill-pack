# Excalidraw Review Checklist

Use this checklist when reviewing an Excalidraw version of a core functional flow diagram before handoff.

## A. 图类型是否正确
- [ ] 这张图是关键流程图 / 状态机，而不是系统架构图
- [ ] 没有偷偷变成部署图、数据模型图、接口定义图
- [ ] 这张图回答的是一个明确的关键流程问题

## B. 主路径与边界
- [ ] 主路径 3 秒内可识别
- [ ] 起点明确
- [ ] 终点明确
- [ ] 成功 / 失败 / pending ownership 的终结态清楚
- [ ] 角色边界或阶段边界清楚

## C. 分支完整性
- [ ] 关键分支都有条件标注
- [ ] 异常路径已表达
- [ ] rollback / compensation 在需要时已表达
- [ ] cancel / retry 在需要时已表达
- [ ] 没有明显遗漏的评审关键分支
- [ ] 没有把同一语义拆成多个视觉噪音节点

## D. 图形语法一致性
- [ ] 同类节点风格一致
- [ ] 同类边语义一致
- [ ] 没有裸线
- [ ] label 不是过长的整句说明
- [ ] 技术产品名没有污染核心语义层

## E. 视觉质量
- [ ] 颜色不超过 3 种语义彩色
- [ ] 节点对齐整齐
- [ ] 容器层级不超过 2 层
- [ ] 文字全部水平
- [ ] 没有环形缠绕到影响阅读
- [ ] 主路径与补偿路径不会互相遮挡

## F. Excalidraw 特有检查
- [ ] Library 元件已复用，而不是每个节点都手工乱画
- [ ] 容器标题位置统一
- [ ] 箭头样式统一（同步/异步/补偿）
- [ ] 如果图已过密，已经拆图而不是继续塞内容
- [ ] 导出前检查缩放比例下文字是否仍可读

## G. 交付检查
- [ ] 图旁边有一句 scope statement：本图回答的关键流程是____
- [ ] 已说明为何选 flowchart 或 state machine
- [ ] 若有 companion artifacts，已明确列出
- [ ] 读者不需要口头解释也能看懂主干逻辑
