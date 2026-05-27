# architect-skill-pack

语言： [English](README.md) | [简体中文](README.zh-CN.md)

**一套可复用、开源、面向架构工作的技能包：覆盖方案调研、解决方案设计、技术概要设计、详细设计、部署交付，以及各类架构图方法。**

当你的架构工作出现这些问题时，可以使用这个仓库：
- 需求还很模糊，就直接进入实现
- 业务方案、技术设计、部署运维被写成一团
- 图虽然很多，但每张图都没回答对问题
- 方案调研太浅，团队反复重复造轮子
- 详细设计不够具体，开发在没有清晰契约和流程的情况下开工

你可以按需采用：
- **单个 skill**
- **单个 bundle**
- **整套技能包**

## 仓库包含什么

本仓库将 17 个 Hermes 兼容技能整理为 3 个公开 bundle：

- **lifecycle-methodology**：架构生命周期分阶段交付方法
- **diagramming**：业务架构图、业务流程图、系统架构图、技术架构图、关键流程图等绘图方法
- **architecture-supplements**：DDD 边界建模、设计模式/重构、技术选型比较方法

## 推荐起步方式

### 如果你的架构工作经常在错误阶段开始
先看：
- `lifecycle-methodology/arch-lifecycle-delivery`
- `lifecycle-methodology/arch-lifecycle-demand-survey-methodology`

### 如果解决方案设计总是写不透
先看：
- `lifecycle-methodology/arch-lifecycle-solution-design-methodology`
- `diagramming/arch-lifecycle-solution-design-biz-flow-diagramming`
- `diagramming/arch-lifecycle-solution-design-biz-arch-diagramming`

### 如果技术设计经常只有原则，没有实现落点
先看：
- `lifecycle-methodology/arch-lifecycle-tech-overview-methodology`
- `lifecycle-methodology/arch-lifecycle-tech-detailed-methodology`
- `diagramming/arch-lifecycle-tech-detailed-core-flow-diagramming`
- `diagramming/arch-lifecycle-tech-detailed-technical-arch-diagramming`

### 如果技术选型经常沦为拍脑袋
先看：
- `architecture-supplements/technology-adoption-comparison`
- `architecture-supplements/ddd-domain-modeling-for-architecture`
- `architecture-supplements/design-patterns-and-refactoring`

## 给 Hermes 的快速安装方式

```bash
git clone https://github.com/xiaohei-info/architect-skill-pack.git
cd architect-skill-pack
mkdir -p ~/.hermes/skills/software-development
cp -R skills/lifecycle-methodology/arch-lifecycle-delivery ~/.hermes/skills/software-development/
```

完整说明见 [`docs/adoption-guide.md`](docs/adoption-guide.md)。

## 这个技能包为什么有价值

这套技能包的核心不是“多几份 prompt”，而是把架构工作中最容易失真的部分沉淀成可复用方法：
- **先调研，再定方案**
- **按阶段产出，不把所有设计揉成一张图**
- **每种图回答不同问题**
- **详细设计要具体到可实现**
- **方案推荐必须写出权衡和验证路径**

## 相关文档

- [`AGENTS.md`](AGENTS.md)
- [`docs/bundles.md`](docs/bundles.md)
- [`docs/adoption-guide.md`](docs/adoption-guide.md)
- [`docs/portability-notes.md`](docs/portability-notes.md)
- [`docs/source-map.md`](docs/source-map.md)

## 许可证

MIT
