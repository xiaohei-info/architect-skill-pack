# Source Basis

This public skill is derived from two source classes:

1. a user-provided technical-architecture drawing draft
2. a private architecture-lifecycle note used to anchor this artifact in the detailed-design stage

Lifecycle basis preserved from the second source:
- 技术架构图 belongs to **详细设计 / 技术架构**
- It must answer:
  - 系统设计中的功能通过什么技术栈实现？如何选型的？
  - 项目结构是什么样的？
  - 系统运行起来后，服务、进程、任务、调用链路如何协作？
  - 稳定性如何保障？
- It sits adjacent to, but must stay distinct from:
  - 项目架构图
  - 关键流程图 / 状态机
  - 数据架构 / ER 图
  - 接口定义文档
  - 非功能性需求设计
  - 部署 / 运维 / 监控 / 容灾文档

Preservation rule:
- the original draft is preserved as a verbatim reference inside this skill package
- the normalized full-detail working reference is preserved as a practical loading reference
- the umbrella `SKILL.md` adds lifecycle placement, review gates, and execution workflow on top of those sources
- if a future summary conflicts with the verbatim draft on drawing detail, exact wording, structure, or example preservation, the verbatim draft wins
